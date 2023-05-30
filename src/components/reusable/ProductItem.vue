<template>
  <li v-for="item in items" :key="item.id" class="selling__item">
    <p v-if="item.sale !== false" class="item__sale">
      - {{ item.sale }} %
    </p>
    <div class="item__body">
      <h3 class="item__title">
        {{ item.name }}
      </h3>
      <p class="item__description">
        {{ item.description.slice(0, 35) + '...' }}
      </p>
      <div class="item__buy">
        <div class="buy__prices">
          <p v-if="item.sale === false" class="buy__price">
            {{ item.price + ' USD' }}
          </p>
          <p v-if="item.sale !== false" class="buy__price">
            {{ (item.price - ((item.price / 100) * item.sale)).toFixed(2) + ' USD' }}
            <span class="buy__price-real">
              {{ item.price.toFixed(2) }}
            </span>
          </p>
        </div>
        <button class="buy__btn">
          Buy now
        </button>
      </div>
    </div>
  </li>
</template>
<script>
  export default {
    props: {
      items: {
        type: Array,
      },
    },
  }
</script>
<style scoped>
  .selling__item {
    width: 269px;
    height: 323px;
    position: relative;
    outline: 1px solid #D1D1D1;
    border-radius: 12px;
    padding: 16px;
  }
  .selling__item::before {
    content: '';
    position: absolute;
    width: 237px;
    height: 180px;
    border-radius: 12px;
    background: #F9F9F9;
    top: 16px;
    left: 16px;
  }
  .selling__item:not(:last-child) {
    margin-right: 32px;
  }
  .item__sale {
    position: absolute;
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 12px;
    color: #6A983C;
    background: #F4F8EC;
    border-radius: 12px;
    top: 28px;
    left: 28px;
    padding: 0 8px;
  }
  .item__body {
    width: 100%;
    position: absolute;
    bottom: 16px;
  }
  .item__title {
    font-family: 'Poppins', sans-serif;
    font-weight: 500;
    font-size: 15px;
    color: #151515;
    margin-bottom: 4px;
  }
  .item__description {
    font-family: 'Open Sans', sans-serif;
    font-weight: 400;
    font-size: 12px;
    color: #575757;
    margin-bottom: 16px;
  }
  .item__buy {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .buy__prices {
    margin-left: 0;
  }
  .buy__price {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 18px;
    color: #151515;
    display: flex;
    flex-direction: column;
  }
  .buy__price-real {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 12px;
    color: #a9a9a9;
    text-decoration: line-through;
    margin-left: 0;
  }
  .buy__btn {
    font-family: 'Poppins', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: #fff;
    cursor: pointer;
    background: #6A983C;
    border: none;
    border: 2px solid #46760A;
    border-radius: 12px;
    padding: 6.5px 12px;
  }
</style>