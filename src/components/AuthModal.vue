<template>
  <div v-if="isVisible" class="modal-overlay">
    <div class="modal">
      <div class="modal-header">
        <h2>{{ isLogin ? 'Авторизация' : 'Регистрация' }}</h2>
        <button class="close-btn" @click="closeModal">&times;</button>
      </div>
      <div class="modal-body">
        <!-- Форма входа -->
        <form v-if="isLogin" @submit.prevent="handleLogin">
          
          <div class="form-group">
            <label for="loginPhone">Номер телефона</label>
            <input type="text" id="loginPhone" v-model="loginPhone" required />
          </div>

          <div class="form-group">
            <label for="loginPassword">Пароль</label>
            <input type="password" id="loginPassword" v-model="loginPassword" required />
          </div>

          <div class="form-group">
            <button type="submit" :disabled="isLoading">Войти</button>
          </div>
        </form>


        <!-- Форма регистрации -->
        <form v-else @submit.prevent="handleRegister">
          <div class="form-group">
            <label for="username">Имя пользователя:</label>
            <input type="text" v-model="registerData.registerUsername" id="username" placeholder="Введите имя пользователя" required />
          </div>

          <div class="form-group">
            <label for="phone">Телефон:</label>
            <input type="text" v-model="registerData.registerPhone" id="phone" placeholder="Введите номер телефона" required />
          </div>

          <div class="form-group">
            <label for="password">Пароль:</label>
            <input type="password" v-model="registerData.registerPassword" id="password" placeholder="Введите пароль" required />
          </div>

          <div class="form-group">
            <label for="passwordConfirm">Подтвердите пароль:</label>
            <input type="password" v-model="registerData.registerPasswordConfirm" id="passwordConfirm" placeholder="Подтвердите пароль" required />
          </div>

          <!-- Отображение сообщения об ошибке -->
          <div v-if="errorMessages" class="error">
            <p>{{ errorMessages }}</p>
          </div>

          <div class="form-group">
            <button type="submit" :disabled="isLoading">Зарегистрироваться</button>
          </div>

          <div v-if="isLoading">Загрузка...</div>
        </form>

        <!-- Переключатель между формами -->
        <div class="switch-form">
          <p v-if="isLogin">
            Нет аккаунта?
            <button @click="toggleForm">Зарегистрируйтесь</button>
          </p>
          <p v-else>
            Уже есть аккаунт?
            <button @click="toggleForm">Войдите</button>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { errorMessages } from 'vue/compiler-sfc';
import axios from 'axios';
export default {
  name: 'AuthModal',
  props: {
    isVisible: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      isVisible: true, // Показываем модальное окно
      isLogin: true, // Начальное состояние - форма входа
      loginData: {
        loginPhone: '',
        loginPassword: '',
      },
      registerData: {
        registerUsername: '',
        registerPhone: '',
        registerPassword: '',
        registerPasswordConfirm: ''
      },
      errorMessages: null,
      isLoading: false
    };
  },

  methods: {
    closeModal() {
      this.$emit('close'); // Закрытие модального окна
    },

    async handleRegister() {
      this.isLoading = true;
      this.errorMessages = '';

      // Проверяем, совпадают ли пароли
      if (this.registerData.registerPassword !== this.registerData.registerPasswordConfirm) {
        this.errorMessages = 'Пароли не совпадают!';
        this.isLoading = false;
        return;
      }

      try {
        // Подготовка данных для отправки на сервер
        const registrationData = {
          username: this.registerData.registerUsername,
          phone: this.registerData.registerPhone,
          password: this.registerData.registerPassword,
        };

        // Отправка POST-запроса на сервер по маршруту /register
        const response = await axios.post('http://localhost:9105/SmakTown/API/register', registrationData);

        // Успешный ответ от сервера
        console.log(response.data.message); // Показать сообщение от сервера

        if (response.status === 200){
          this.isLogin = true;
          this.isLoading = false;

        } else{
          this.errorMessages = 'Ошибка при регистрации. Попробуйте снова.';
          this.isLoading = false;
        }
      } catch (error) {
        // Обработка ошибок
        if (error.response && error.response.data) {
          // Если ошибка от сервера (например, ошибка валидации)
          this.errorMessages = error.response.data.error;
        } else {
          // Если ошибка сети или другие ошибки
          this.errorMessages = 'Произошла ошибка при регистрации';
        }
      }
       
    },
    toggleForm() {
      this.isLogin = !this.isLogin; // Переключаем состояние между формами
    },
    async handleLogin() {
      this.isLoading = true;
      this.errorMessages = '';

      // Подготовка данных для отправки на сервер
      const loginData = {
        phone: this.loginPhone,  // Используем данные из v-model
        password: this.loginPassword,
      };

      try {
        // Отправка POST-запроса на сервер
        const response = await axios.post('http://localhost:9105/SmakTown/API/signIn', loginData);

        // Успешный ответ от сервера
        
        console.log('короче все норм')
        if (response.status === 200){
          this.isLogin = true;
          this.isLoading = false;

        } else{
          this.errorMessages = 'Ошибка при регистрации. Попробуйте снова.';
          this.isLoading = false;
        }

        
      } catch (error) {
        // Обработка ошибок
        if (error.response && error.response.data) {
          this.errorMessages = error.response.data.error;
        } else {
          this.errorMessages = 'Произошла ошибка при авторизации';
        }
      } finally {
        // Остановка индикатора загрузки
        this.isLoading = false;
        this.closeModal();  // Закрыть модальное окно после регистрации
      }
    }


  },
};
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal {
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  width: 300px;
  max-width: 100%;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.modal-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.close-btn {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
}

.modal-body {
  margin-top: 20px;
}

.form-group {
  margin-bottom: 15px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
}

.form-group input {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.form-group button {
  width: 100%;
  padding: 10px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.form-group button:hover {
  background-color: #45a049;
}

.switch-form {
  margin-top: 15px;
  text-align: center;
}

.switch-form button {
  background: none;
  border: none;
  color: #4caf50;
  cursor: pointer;
  font-size: 14px;
}

.switch-form button:hover {
  text-decoration: underline;
}
</style>
