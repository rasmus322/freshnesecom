<template>
  <div class="selling__container container">
    <LeftSideMenu :title="menuTitle" :items="menuList" :btn="menuBtn"/>
    <ul class="selling__list">
      <ProductItem :items="productItems"/>
    </ul>
  </div>
</template>
<script>
  import LeftSideMenu from './reusable/LeftSideMenu.vue';
  import ProductItem from './reusable/ProductItem.vue';

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
        productItems: [
          {
            id: 7,
            name: 'Fridge',
            description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            img: '../../public/imgs/selling_item_bg.png',
            price: 36,
            sale: 45
          },
          {
            id: 2,
            name: 'Knife',
            description: 'Ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            img: '../../public/imgs/selling_item_bg.jpeg',
            price: 10.28,
            sale: false
          },
          {
            id: 3,
            name: 'Diapers',
            description: 'Dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
            img: '../../public/imgs/selling_item_bg.jpeg',
            price: 1.48,
            sale: 36
          },
        ],
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