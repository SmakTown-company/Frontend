<template>
  <div class="sale-card">
    <!-- Поисковик -->
    <div class="search-container">
      <input 
        type="text" 
        v-model="searchQuery" 
        placeholder="Поиск по сайту" 
        class="search-input" 
      />
      <button @click="performSearch" class="search-button">
        <span class="search-icon"></span> найти
      </button>
    </div>
    <div class="card-sale-list">
      <div class="card" v-for="(product, index) in products" :key="index" :class="{'image-card': index === 2}">
        <!-- Для третьей карточки добавляем класс "image-card" -->
        <div v-if="index === 2" class="img-for-card image-button">
          <img :src="`/src/assets/card-image.png`" alt="image-button" class="product-image" />
        </div>
        <!-- Для всех остальных карточек -->
        <div v-else>
          <div class="img-for-card">
            <img :src="`/src/assets/${product.image}`" alt="product.name" class="product-image" />
          </div>
          <div class="name-product">
            <h3>{{ product.name }}</h3>
          </div>
          <div class="price">
            <h3>{{ product.price }}</h3>
          </div>
          <div class="actions">
            <button class="basket-button">
              В КОРЗИНУ
            </button>
            <button class="favorite-button">
              <span class="favorite-icon"></span>
            </button>
          </div>
          <div class="shop">
            {{ product.shop }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: "", // Переменная для хранения поискового запроса
      products: [
        { 
          name: "Куриное филе", 
          price: "350₽", 
          shop: "ООО 'ПУД', Симферополь ул. Жукова, д. 12",
          image: "image.png" 
        },
        { 
          name: "CocaCola 0.475", 
          price: "100₽", 
          shop: "ООО 'Корзина', Симферополь, ул. Гайдара, д. 132",
          image: "image.png" 
        },
        {

        },
        { 
          name: "Мясная закуска 250г 'Бавария'", 
          price: "220₽", 
          shop: "ООО 'Еда-Вода', Симферополь, ул. Скуфская, д. 42В",
          image: "image.png" 
        },
        // добавьте другие продукты, если нужно
      ]
    };
  },
  methods: {
    performSearch() {
      if (this.searchQuery.trim()) {
        console.log("Поисковый запрос:", this.searchQuery);
        // Логика обработки поиска
      } else {
        console.log("Введите запрос для поиска.");
      }
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  user-select: none;
}

body {
  font-family: 'Montserrat', sans-serif;
}

.sale-card {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  background-color: #f2f4f0;
  width: 100vw;
  min-height: 55vh;
  border-radius: 25px;
}

.card-sale-list {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  justify-content: center;
}

.card {
  background-color: white;
  width: 100%;
  min-height: 400px;
  border-radius: 15px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.card:hover {
  transform: scale(1.05);
}

/* Стиль для третьей карточки */
.card.image-card {
  min-height: 400px;
  padding: 0; /* Убираем отступы */
  background-color: transparent; /* Убираем фон */
  display: flex;
  justify-content: center;
  align-items: center;
}

.card.image-card .img-for-card {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 15px;
}

.card.image-card .product-image {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Картинка полностью заполняет карточку */
  border-radius: 15px;
}

.img-for-card {
  width: 100%;
  height: 200px;
  border-radius: 15px;
  background-color: #e0e0e0;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden; /* Обрезка изображения */
}

.product-image {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Адаптация изображения к размеру блока */
}

.name-product {
  margin-top: 10px;
  text-align: left;
}

.price {
  font-size: 1.2rem;
  font-weight: 600;
  color: #333;
  text-align: left;
}

.actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 15px;
}

.basket-button {
  padding: 5px 20px;
  font-size: 16px;
  font-weight: bold;
  min-height: 35px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  color: white;
  background-color: #f5b461;
  flex-grow: 1;
  text-align: center;
}

.basket-button:hover {
  background-color: #f39c12;
}

.favorite-button {
  width: 30px;
  height: 30px;
  background-color: #d3d3d3;
  border: none;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 10px;
  cursor: pointer;
}

.favorite-button:hover {
  background-color: #b0b0b0;
}

.favorite-icon {
  width: 20px;
  height: 20px;
  background: url('@/assets/favorite.svg') no-repeat center;
  background-size: contain;
}

.shop {
  font-size: 0.7rem; /* Уменьшаем размер шрифта */
  margin-top: 10px;
  line-height: 1.4; /* Увеличение межстрочного интервала для лучшей читаемости */
}

.search-container {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.search-input {
  width: 1040px;
  padding: 12px;
  border-radius: 15px;
  font-size: 16px;
  border: none;
  outline: none;
}

.search-button {
  padding: 12px 20px;
  margin-left: 10px;
  background-color: #f2bd6a; /* Цвет кнопки */
  border: none;
  border-radius: 12px;
  font-size: 16px;
  font-weight: 600;
  color: #fff; /* Белый цвет текста */
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5px; /* Расстояние между иконкой и текстом */
  outline: none; /* Удалить обводку при клике */
}
.search-button:hover {
  background-color: #f39c12; /* Цвет кнопки при наведении */
}
/* Добавляем SVG-иконку для кнопки */
.search-icon {
  width: 16px;
  height: 16px;
  display: inline-block;
  background: url('@/assets/lupa.svg') no-repeat center;
  background-size: contain;
}

</style>
