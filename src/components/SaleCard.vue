<template>
    <div class="sale-card">
        <div class="search-box">
            <nav class="navbar navbar-light bg-light">
                <form class="form-inline" @submit.prevent="openSearchModal">
                  <input class="form-control mr-sm-2 search__engin" type="text" placeholder="поиск по сайту" v-model="searchQuery">
                  <button type="submit" class="btn btn-outline-secondary search__button">найти</button>
                </form>
            </nav>
        </div>

    </div>

</template>

<script>

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');
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


.sale-card{
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #ffffff; /* Фон баннера */
    width: 100vw; /* Баннер на всю ширину экрана */
    height: auto; /* Автоматическая высота */
    min-height: 50vh; /* Минимальная высота */
    margin: 0 auto; /* Центрируем, если есть родитель с отступами */
    box-sizing: border-box;
    margin-top: 0px; /* Убираем отступ сверху */
    border-radius: 25px;
    
  
}

.search-box{
    
}

</style>