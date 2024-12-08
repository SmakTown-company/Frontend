<template>
  <header class="header">
    <div class="container">
      <!-- Логотип -->
      <div class="logo">
        <img src="./icons/logo.png" alt=" " class="logo-image" />
        <span class="logo-text">Смактаун</span>
      </div>
      <!-- Навигация -->
      <nav class="navigation">
        <a href="#" class="nav-link active">Главная</a>
        <a href="#" class="nav-link">Корзина</a>
        <a href="#" class="nav-link">Сотрудничество</a>
      </nav>
      <!-- Локация и профиль -->
      <div class="user-actions">
        <a href="#" class="location">
          <svg class="location-icon" width="24" height="24" viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
            <path d="M24 4c-7.73 0-14 6.27-14 14 0 10.5 14 26 14 26s14-15.5 14-26c0-7.73-6.27-14-14-14zm0 19c-2.76 0-5-2.24-5-5s2.24-5 5-5 5 2.24 5 5-2.24 5-5 5z"/>
            <path d="M0 0h48v48h-48z" fill="none"/>
          </svg>
          Симферополь
        </a>
        <a href="#" class="profile">
          <i class="fa fa-user"></i> Профиль
        </a>
      </div>
    </div>
  </header>
</template>

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
  font-family: Arial, sans-serif;
}

a {
  text-decoration: none;
  outline: none;
}

.header {
  user-select: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #111;
  color: white;
  z-index: 1000;
  padding: 10px 0; /* Оставляем небольшой отступ внутри хедера */
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
  height: 60px; /* Фиксированная высота хедера */
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
  color: #ffcc00;
}

.nav-link:hover {
  color: #ffcc00;
  background-color: transparent;
}

.user-actions {
  display: flex;
  align-items: center;
  gap: 20px;
}

.location,
.profile {
  font-size: 14px;
  color: white;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 5px 10px;
  border-radius: 5px;
  transition: color 0.3s ease, background-color 0.3s ease;
}

.location:hover,
.profile:hover {
  color: #ffcc00;
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
  fill: #ffcc00;
}
</style>