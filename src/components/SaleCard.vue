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
    <div class="sale-text">
      <h2>Товары по скидке</h2>
    </div>
    <div class="card-sale-list">
      <div class="card">
        <div class="img-for-card">
          
        </div>
        <div class="name-product">
          <h3>Куриное филе</h3>
        </div>
        <div class="price">
          <h3>350₽</h3>
        </div>
        <div class="in-basket">
          <h2>В КОРЗИНУ</h2>
        </div>
        <div class="reviews">

        </div>
        <div class="shop">
          ООО "ПУД", Симферополь ул. Жукова, д. 12

        </div>

      </div>
      
      <div class="card">
        penis
      </div>
      <div class="card">
        penis
      </div>
      <div class="card">
        penis
      </div>

    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchQuery: "", // Переменная для хранения поискового запроса
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
}

body {
  font-family: 'Montserrat', sans-serif;
}

a {
  text-decoration: none;
  outline: none;
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

.search-container {
  display: flex;
  align-items: center;
  margin-top: 20px;
}

.search-input {
  width: 1000px;
  padding: 13px;
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

.sale-text{
  font-weight: bold;
  margin-right: 880px;
  margin-top: 20px;
  margin-bottom: 20px;
  color: #111111;
}

.card-sale-list{
  width: 100%;
  display: flex;

}

.card{
  background-color: white;
  min-width: 260px;
  min-height: 350px;
  border-radius: 15px;
  margin-left: 25px;
  padding: 20px;
  
  

  
}
.img-for-card{
  
  min-height: 200px;
  border-radius: 15px;
  background-color: red;
}
</style>
