<template>
  <div class="selling__container container">
    <LeftSideMenu :title="menuTitle" :items="menuList" :btn="menuBtn"/>
    <ul class="selling__list">
      <ProductItem :items="sellItems"/>
    </ul>
  </div>
</template>
<script>
  import LeftSideMenu from './reusable/LeftSideMenu.vue';
  import ProductItem from './reusable/ProductItem.vue';
  import items from '../data/items.js'

  export default {
    components: { LeftSideMenu, ProductItem, },
    data() {
      return {
        menuTitle: 'Best selling products',
        menuList: [
          {id: 1, name: 'Kitchen'},
          {id: 2, name: 'Meat and fish'},
          {id: 3, name: 'Special nutrition'},
          {id: 4, name: 'Pharmacy'},
          {id: 5, name: 'Baby'},
        ],
        menuBtn: 'More products',
        sellItems: items.filter(item => item.popularity > 5).slice(0, 3)
      }
    },
  }
</script>
<style scoped>
  .selling__container {
    display: flex;
    justify-content: space-between;
    padding: 64px 45px;
  }
  .selling__list {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-right: 0;
  }
</style>