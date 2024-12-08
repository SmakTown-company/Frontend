<template>
  <div id="app">
    <Header />
    <Banner />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Banner from "./components/Banner.vue";

export default {
  name: "App",
  components: {
    Header,
    Banner,
  },
};
</script>

<style>
body {
  margin: 0; /* Убираем стандартные отступы браузера */
}

#app {
  margin: 0; /* Убираем отступы у корневого элемента */
  padding: 0; /* Убираем отступы у корневого элемента */
  box-sizing: border-box; /* Применяем border-box для всех элементов */
}
</style>