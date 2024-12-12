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
            <label for="loginUsername">Логин</label>
            <input type="text" id="loginUsername" v-model="loginUsername" required />
          </div>
          <div class="form-group">
            <label for="loginPassword">Пароль</label>
            <input type="password" id="loginPassword" v-model="loginPassword" required />
          </div>
          <div class="form-group">
            <button type="submit">Войти</button>
          </div>
        </form>

        <!-- Форма регистрации -->
        <form v-else @submit.prevent="handleRegister">
          <div class="form-group">
            <label for="registerUsername">Логин</label>
            <input type="text" id="registerUsername" v-model="registerUsername" required />
          </div>
          <div class="form-group">
            <label for="registerPassword">Пароль</label>
            <input type="password" id="registerPassword" v-model="registerPassword" required />
          </div>
          <div class="form-group">
            <label for="registerPasswordConfirm">Повторите пароль</label>
            <input type="password" id="registerPasswordConfirm" v-model="registerPasswordConfirm" required />
          </div>
          <div class="form-group">
            <button type="submit">Зарегистрироваться</button>
          </div>
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
      isLogin: true, // Состояние для переключения между формами
      loginUsername: '',
      loginPassword: '',
      registerUsername: '',
      registerPassword: '',
      registerPasswordConfirm: '', // Поле для повторного ввода пароля
    };
  },
  methods: {
    closeModal() {
      this.$emit('close'); // Эмитим событие для закрытия модального окна
    },
    handleLogin() {
      console.log('Авторизация', this.loginUsername, this.loginPassword);
      this.closeModal();
    },
    handleRegister() {
      // Проверка совпадения паролей
      if (this.registerPassword !== this.registerPasswordConfirm) {
        alert('Пароли не совпадают!');
        return;
      }
      console.log('Регистрация', this.registerUsername, this.registerPassword);
      this.closeModal();
    },
    toggleForm() {
      this.isLogin = !this.isLogin; // Переключаем состояние между формами
    },
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