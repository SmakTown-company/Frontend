<template>
  <div class="banner">
    <div class="banner-content">
      <img class="banner-image" src="@/assets/banner.svg" alt="Banner Illustration" />
      <div class="banner-text">
        <h1 class="banner-title">смактаун.</h1>
        <p class="banner-subtitle">всё, что нужно — к дому.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
};
</script>

<style scoped>

/* Универсальный сброс стилей */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

/* Основной стиль баннера */
.banner {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #111; /* Фон баннера */
  width: 100vw; /* Баннер на всю ширину экрана */
  height: auto; /* Автоматическая высота */
  min-height: 70vh; /* Минимальная высота */
  margin: 0 auto; /* Центрируем, если есть родитель с отступами */
  box-sizing: border-box;
  margin-top: 0; /* Убираем отступ сверху */
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
  color: #f1c40f; /* Цвет текста */
}

/* Изображение в баннере */
.banner-image {
  flex-shrink: 0; /* Запрещаем сжимать изображение */
  width: 50%; /* Половина ширины для изображения */
  max-width: 600px; /* Максимальная ширина */
}

/* Текст в баннере */
.banner-text {
  margin-left: 2rem; /* Отступ от изображения */
  text-align: left;
}

/* Стили заголовка */
.banner-title {
  font-size: 3.5rem; /* Размер заголовка */
  font-weight: bold;
  margin: 0;
}

/* Стили подзаголовка */
.banner-subtitle {
  font-size: 1.75rem;
  font-weight: lighter;
  margin: 0;
}
</style>