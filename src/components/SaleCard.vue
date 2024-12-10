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
  min-height: 50vh;
  border-radius: 25px;
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
