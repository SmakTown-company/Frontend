<template>
  <div class="banner">
    <div class="banner-content">
      <img class="banner-image" src="@/assets/banner.svg" alt="Banner Illustration" />
      <div class="banner-text">
        <h1 class="banner-title">смактаун.</h1>
        <p class="banner-subtitle2">всё, что нужно</p>
        <p class="banner-subtitle">— к дому.</p>
      </div>

    </div>
    
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');
/* Универсальный сброс стилей */
*, *::before, *::after {
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
  margin: 0;
  padding: -10px;
}

p {
  margin-right: 50px;
}

/* Основной стиль баннера */
.banner {
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: url('@/assets/background.svg'); /* Подключение SVG-фона */
  background-size: 100% 100%;
  background-repeat: no-repeat; /* Запрещаем повторение изображения */
  background-position: center; /* Центрируем фон */
  width: 100vw; /* Баннер на всю ширину экрана */
  height: auto; /* Автоматическая высота */
  min-height: 70vh; /* Минимальная высота */
  margin: 0 auto; /* Центрируем, если есть родитель с отступами */
  box-sizing: border-box;
  margin-top: 0px; /* Убираем отступ сверху */
}

/* Контент внутри баннера */
.banner-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px; /* Ограничиваем ширину контента */
  width: 100%;
  padding: 1rem; /* Внутренние отступы */
  color: #f2bd6a; /* Цвет текста */
}

/* Изображение в баннере */
.banner-image {
  flex-shrink: 0; /* Запрещаем сжимать изображение */
  width: 50%; /* Половина ширины для изображения */
  max-width: 600px; /* Максимальная ширина */
}

/* Текст в баннере */
.banner-text {
  margin-left: 3.5rem; /* Отступ от изображения */
  text-align: left;
  line-height: 65px;
}

/* Стили заголовка */
.banner-title {
  font-size: 3.5rem; /* Размер заголовка */
  font-weight: 800;
  margin-left: 80px;
}

/* Стили подзаголовка */
.banner-subtitle {
  font-size: 3.5rem; /* Размер заголовка */
  font-weight: 800;
  margin-left: 80px;
}

.banner-subtitle2 {
  font-size: 3.5rem; /* Размер заголовка */
  font-weight: 800;
  margin: 0;
}
</style>
