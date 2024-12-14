<template>
  <header class="header">
    <div class="container">
      <!-- Логотип -->
      <div class="logo">
        <svg 
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          width="81px" height="48px">
          <image  x="20px" y="0px" width="61px" height="48px"  xlink:href="data:img/png;base64,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" />
        </svg>
        <span class="logo-text">cмактаун</span>
      </div>
      <!-- Навигация -->
      <div class="navigation">
      <button class="main-module"> Главная</button>
      <button class="basket-module" @click="openBasketModal">Корзина</button>
      <button class="cooperation-module"> Сотрудничество</button>

       <!-- Модальное окно корзины -->
        <BasketModal 
          :isVisible="isBasketVisible" 
          :basketItems="basketItems"
          @update:isVisible="isBasketVisible = $event"
          @update:basketItems="basketItems = $event"
        />
      </div>
      <!-- Локация и профиль -->
      <div class="user-actions">
        <button class="location">
          <svg 
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            width="26px" height="30px">
            <image  x="0px" y="0px" width="20px" height="30px"  xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAeCAMAAAAFBf7qAAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAABBVBMVEXj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Oz///94+Cg9AAAAVXRSTlMAF1qYwdzgzKpyLSKS6fq3SWTsnQx5vRKByBBUpxPkUnfNAwbXPTiNzmBQocec0g6I47Qm+++1diObEYpwZabFOpAIQgThTowWGYsYz5XUIBqO0H3toAdLAwAAAAFiS0dEVgoN6YkAAAAHdElNRQfoDAgULyl9Bl0MAAAA8klEQVQoz3XS6VbCMBAF4AuyFamIWlQQBQFxrQu4lVWUTRQVnfd/FVuJSVqS+ytzvtNkemYAllB4JRKNxRNGEv6spkxiWUuvy5LZIDmbW1wsCiS7zWSHlrKb+5M8KbLnSWFfRXTgUlEpVDpEuaImquJII1SDIYrjk9MzUZ3jgp/tS/flK15e44afLa/feuO/vMUdp3uPHiR6FBc6LjWlC1viYbud74iqi56u+Sf0oxp6VkyE/eQL4AyUNNQOJbEY5WhZ7DEbczMo8Qlfjle/lKbSSvnufJvI24Z3IbOPwJLW+DefCOZLK8zmKgG+zZ+01MEvAqGwBNylKVAAAAAASUVORK5CYII=" />
          </svg>
          Симферополь
        </button>
           <!-- Модальное окно -->
           <button class="profile" @click="openAuthModal">
          <svg 
            xmlns="http://www.w3.org/2000/svg"
            xmlns:xlink="http://www.w3.org/1999/xlink"
            width="26px" height="30px">
            <image  x="0px" y="0px" width="20px" height="30px"  xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB4AAAAfCAMAAADHso01AAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAABFFBMVEX////j6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Ozj6Oz///+kvwCpAAAAWnRSTlMAU6/n8tmYMwm0hNKRo1Ex8AOnV60v3E7tBwo+5AEP/MLGe1sZ3Y8p2kb50RIg/u6CHUtZPQwYZmgjRG0eE/iWNg65/ZJg7+O8yvHqVJV/n3yATC3ALrqTlGez1IrBAAAAAWJLR0QAiAUdSAAAAAd0SU1FB+gMCBQrLR4HXBEAAAD1SURBVCjPfdP7VwFBFMDxm0RlYzwqekhLFFJeFSmhokRJD+7//4e01WLu7N39/jR7PufMmb1zBkBqybXsXvF4gW11Df9bZ9mHszRGN3CR36IBSVEEVQ7JjGFFg4JwROFNoril8DblaIyyn7LYobxLeW+fcvyAcEL9sUPCuspJwinL2I4kTVtnnlnoMXdjJ1lTc3n2Rk9DBQPPzsGuYqlcqXJwcXlVm3/U9euGjDfarbFt8+53Vq1S21h37uNzfXg0D9VN9J6ezXX/xdQB8g3/9BXtejN0hPa9w9hBUcCHExfASdEtvQ0u+BQO+gXQ0L8nbANtCj9/vK8c/Y8zbAAAAABJRU5ErkJggg==" />
          </svg>
          Профиль
        </button>
      </div>
    </div>
  </header>
</template>

<script>
import BasketModal from './BasketModal.vue';

export default{
  data() {
    return {
      isBasketVisible: false,
      basketItems: []  // Тут будут храниться товары корзины
    };
  },
  components: {
    BasketModal
  },
  methods: {
    openAuthModal() {
      this.$emit('open-modal'); // Эмитим событие для открытия модального окна
    },
    openBasketModal() {
      this.isBasketVisible = true;  // Открыть модальное окно
    },
  },
};
</script>



<style scoped>
/* Подключаем шрифт Montserrat */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');

/* Применяем шрифт ко всему хедеру */
.header {
  font-family: 'Montserrat', sans-serif; /* Применяем Montserrat */
}

/* Остальные стили */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Montserrat', sans-serif;
}

a {
  text-decoration: none;
  outline: none;
}

.header {
  user-select: none;
  position: fixed;
  top: 0px;
  left: 0;
  width: 100%;
  background-color: #111;
  color: white;
  z-index: 1000;
  padding: 10px 0; /* Оставляем небольшой отступ внутри хедера */
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
  height: 70px; /* Фиксированная высота хедера */
  border-bottom: solid 0px;
  border-color: rgb(104, 104, 104);
}


.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
}

.logo-image {
  height: 40px;
}

.logo-text {
  font-size: 18px;
  font-weight: bold;
  color: white;
}

.navigation {
  display: flex;
  gap: 30px;
  
}


.nav-link {
  color: white;
  text-decoration: none;
  font-size: 16px;
  transition: color 0.3s ease, background-color 0.3s ease;
  padding: 5px 10px;
  border-radius: 5px;
}

.nav-link.active {
  color: #f2bd6a;
}

.nav-link:hover {
  color: #f2bd6a;
  background-color: transparent;
}

.user-actions {
  display: flex;
  align-items: center;
  gap: 20px;
}

.location,
.profile,
.main-module,
.basket-module,
.cooperation-module {
  font-size: 16px;
  color: white;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 2px;
  padding: 5px 10px;
  border-radius: 5px;
  transition: color 0.3s ease, background-color 0.3s ease;

  
}


.location:hover,
.profile:hover,
.main-module:hover,
.basket-module:hover,
.cooperation-module:hover {
  color: #f2bd6a;
  background-color: transparent;
}

.location i,
.profile i {
  font-size: 16px;
}

.location-icon {
  fill: white;
  width: 24px;
  height: 24px;
  transition: fill 0.3s ease;
}

.location:hover .location-icon {
  fill: #f2bd6a;
}
button {
  background: none;
  border: none;
  padding: 0;
  font-size: inherit;
  font-family: inherit;
  color: inherit;
  cursor: pointer;
  text-decoration: underline; /* Сделать кнопки похожими на текст */
}

button:focus {
  outline: none; /* Убирает фокус */
}

/* Стили для иконок в кнопках */
button svg {
  vertical-align: middle; /* Выравнивание иконок по центру */
  margin-right: 8px; /* Отступ от текста */
}
</style>




