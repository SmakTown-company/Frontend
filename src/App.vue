<template>
  <div id="app">
    <Header />
    <Banner />
    <SaleCard />
  </div>
</template>

<script>

import Header from "./components/Header.vue";
import Banner from "./components/Banner.vue";
import SaleCard from "./components/SaleCard.vue";

export default {
  name: "App",
  components: {
    Header,
    Banner,
    SaleCard,
  },
};
</script>

<style>

body {
  margin: 0; /* Убираем стандартные отступы браузера */
  min-height: 0vh;
}

#app {
  margin: 0; /* Убираем отступы у корневого элемента */
  padding: 0; /* Убираем отступы у корневого элемента */
  box-sizing: border-box; /* Применяем border-box для всех элементов */
  background-color: #111;
}

</style>