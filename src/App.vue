<template>
  <div id="app">
    <!-- Подключаем Header -->
    <Header @open-modal="toggleModal" />

    <!-- Подключаем остальные компоненты -->
    <Banner />
    <SaleCard />
    <AdvertisementBanner />
    <ProductCard />
    <BasketModal />


    <!-- Модальное окно -->
    <AuthModal :isVisible="isModalVisible" @update:isVisible="isModalVisible = $event" />

  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Banner from "./components/Banner.vue";
import SaleCard from "./components/SaleCard.vue";
import ProductCard from "./components/ProductCard.vue";
import AdvertisementBanner from "./components/AdvertisementBanner.vue";
import AuthModal from "./components/AuthModal.vue";
import BasketModal from "./components/BasketModal.vue";

export default {
  name: "App",
  components: {
    Header,
    Banner,
    SaleCard,
    ProductCard,
    AdvertisementBanner,
    AuthModal,
    BasketModal,
  },
  data() {
    return {
      isModalVisible: false, // Управление видимостью модального окна
    };
  },
  methods: {
    toggleModal() {
      this.isModalVisible = !this.isModalVisible; // Переключаем видимость модального окна
    },
  },
};
</script>

<style>
body {
  margin: 0;
  min-height: 0vh;
}

#app {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #111;
}
</style>