<template>
  <div class="sales__container container">
    <div class="sales__top">
      <h2 class="sales__title">
        The biggest sales
      </h2>
      <MainBtn :name="name"/>
    </div>
    <ul class="sales__list">
      <ProductItem :items="saleItems"/>
    </ul>
  </div>
</template>
<script>
  import ProductItem from './reusable/ProductItem.vue';
  import MainBtn from './reusable/MainBtn.vue';
  import items from '../data/items.js'

  export default {
    components: { ProductItem, MainBtn },
    data() {
      return {
        name: 'Go to all sales',
        saleItems: items.filter(item => item.sale).slice(0, 4)
      }
    }
  }
</script>
<style scoped>
  .sales__container {
    padding: 70px 45px;
  }
  .sales__top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 32px;
  }
  .sales__title {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 18px;
    color: #151515;
    margin-left: 0;
  }
  .sales__list {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>