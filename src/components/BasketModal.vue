<template>
    <div v-if="isVisible" class="modal-overlay">
      <div class="modal-basket">
        <div class="modal-header">
          <h2>Корзина</h2>
          <!-- Модальное окно корзины -->
          <BasketModal :isVisible="isBasketVisible" :basketItems="basketItems" @update:isVisible="isBasketVisible = $event" />

          <button class="close-btn" @click="closeModal">&times;</button>
        </div>
        <div class="modal-body">
          <div v-if="basketItems.length > 0">
            <ul class="basket-items">
              <li v-for="(item, index) in basketItems" :key="item.id" class="basket-item">
                <div class="item-info">
                  <span class="item-name">{{ item.name }}</span>
                  <span class="item-price">{{ formatPrice(item.price) }} ₽</span>
                </div>
                <button class="remove-item-btn" @click="removeItem(index)">Удалить</button>
              </li>
            </ul>
            <div class="basket-summary">
              <span class="total">Итог: {{ formatPrice(totalPrice) }} ₽</span>
              <button class="checkout-btn" @click="checkout">Оформить заказ</button>
            </div>
          </div>
          <div v-else class="empty-basket">
            <p>Ваша корзина пуста.</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "BasketModal",
    props: {
      isVisible: {
        type: Boolean,
        default: false, // Контроль видимости модального окна
      },
      basketItems: {
        type: Array,
        default: () => [], // Массив товаров в корзине
      },
    },
    computed: {
      // Считаем общую сумму корзины
      totalPrice() {
        return this.basketItems.reduce((total, item) => total + item.price, 0);
      },
    },
    methods: {
      // Форматирование цены
      formatPrice(price) {
        return price.toFixed(2); // Округляем до 2 знаков после запятой
      },
      // Закрытие модального окна
      closeModal() {
        // Передаем информацию родительскому компоненту
        this.$emit('update:isVisible', false);
      },
      // Удаление товара из корзины
      removeItem(index) {
        const newBasketItems = [...this.basketItems];
        newBasketItems.splice(index, 1);
        // Передаем обновленный список товаров родительскому компоненту
        this.$emit('update:basketItems', newBasketItems);
      },
      // Оформление заказа
      checkout() {
        console.log('Оформление заказа', this.basketItems);
        this.closeModal(); // Закрываем окно после оформления
      },
    },
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
  }
  
  .modal-basket {
    background: #fff;
    padding: 20px;
    border-radius: 8px;
    width: 400px;
    max-width: 100%;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  }
  
  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .close-btn {
    background: none;
    border: none;
    font-size: 20px;
    cursor: pointer;
  }
  
  .modal-body {
    margin-top: 20px;
  }
  
  .basket-items {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  
  .basket-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 15px;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
  }
  
  .item-info {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }
  
  .item-name {
    font-weight: bold;
  }
  
  .remove-item-btn {
    background: none;
    border: none;
    color: red;
    cursor: pointer;
  }
  
  .basket-summary {
    margin-top: 20px;
    text-align: right;
  }
  
  .checkout-btn {
    background-color: #4caf50;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .checkout-btn:hover {
    background-color: #45a049;
  }
  
  .empty-basket {
    text-align: center;
    font-size: 18px;
    color: #888;
  }
  </style>
  