<template>
  <div class="sale-card">
    <div class="card-sale-list">
      <div class="card" v-for="(product, index) in products" :key="index">
        <div class="img-for-card">
          
        </div>
        <div class="name-product">
          <h3>{{ product.nameproduct }}</h3>
        </div>
        <div class="price">
          <h3>{{ product.price }}</h3>
        </div>
        <div class="actions">
          <button class="basket-button" @click="addToBasket(product)">
            В КОРЗИНУ
          </button>
          <button class="favorite-button">
            <span class="favorite-icon"></span>
          </button>
        </div>
        <div class="shop">
          {{ product.shop_id }}
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
      products: [], // Массив для хранения полученных карт
    };
  },
  mounted() {
    this.fetchCards(); // Загружаем карты при монтировании компонента
  },
  methods: {
    // Метод для выполнения HTTP-запроса и получения всех карт
    fetchCards() {
    fetch('http://localhost:8080/SmakTown/API/getAllCards')
      .then((response) => {
        if (!response.ok) {
          throw new Error('Ошибка при загрузке карт');
        }
        return response.json();
      })
      .then((data) => {
        console.log(data); // Логирование данных, полученных с сервера
        this.products = data;
      })
      .catch((error) => {
        console.error('Ошибка:', error);
      });
    },
    // Метод для добавления товара в корзину
    addToBasket(product) {
      fetch('http://localhost:8080/SmakTown/API/addInBasket', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          id: product.id, // передаем id товара
        }),
      })
        .then((response) => response.json())
        .then((data) => {
          if (data.success) {
            // После успешного добавления товара, обновляем локальную корзину
            this.basketItems.push(product);
            console.log('Товар добавлен в корзину:', product);
          } else {
            console.error('Ошибка при добавлении товара в корзину');
          }
        })
        .catch((error) => {
          console.error('Ошибка при добавлении товара в корзину:', error);
        });
    }

  },
};
</script>

<style scoped>
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
  margin-top: 50px;
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
</style>
