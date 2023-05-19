<template>
  <div class="category__container container">
    <LeftSideMenu :items="menuList" :title="menuTitle" :btn="menuBtn"/>
    <div class="category__banners">
      <div class="category__banner">
        <p class="banner__subtitle">
          Banner subfocus
        </p>
        <h3 class="banner__title">
          Space for heading
        </h3>
        <a href="" class="banner__link">
          Read recepies
          <svg width="7" height="9" viewBox="0 0 7 9" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M2.0332 7.68669L4.7732 4.94669C4.89737 4.82178 4.96706 4.65281 4.96706 4.47669C4.96706 4.30056 4.89737 4.13159 4.7732 4.00669L2.10654 1.34002" stroke="#6A983C" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="bevel"/>
          </svg>
        </a>
      </div>
      <div class="category__banner">
        <p class="banner__subtitle">
          Banner subfocus
        </p>
        <h3 class="banner__title">
          Space for heading
        </h3>
        <a href="" class="banner__link">
          Read recepies
          <svg width="7" height="9" viewBox="0 0 7 9" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M2.0332 7.68669L4.7732 4.94669C4.89737 4.82178 4.96706 4.65281 4.96706 4.47669C4.96706 4.30056 4.89737 4.13159 4.7732 4.00669L2.10654 1.34002" stroke="#6A983C" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="bevel"/>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>
<script>
  import LeftSideMenu from './reusable/LeftSideMenu.vue';

  export default {
    components: { LeftSideMenu },
    data() {
      return {
        menuTitle: 'Category menu',
        menuList: [
          {id: 1, name: 'Bakery'},
          {id: 2, name: 'Fruit and vegetables'},
          {id: 3, name: 'Meat and fish'},
          {id: 4, name: 'Drinks'},
          {id: 5, name: 'Kitchen'}
        ],
        menuBtn: 'More categories'
      }
    }
  }
</script>
<style scoped>
  .category__container {
    height: 410px;
    display: flex;
    justify-content: space-between;
    padding: 64px 45px;
  }
  .category__banners {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-right: 0;
    margin-left: 0;
  }
  .category__banner {
    width: 419px;
    height: 100%;
    position: relative;
    background: #F4F8EC;
    background-image: url('../../public/imgs/category_banners_bg.svg');
    background-repeat: no-repeat;
    background-size: contain;
    border-radius: 12px;
    padding: 48px 0 33px 32px;
  }
  .category__banner:not(:last-child) {
    margin-right: 32px;
  }
  .banner__subtitle {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 12px;
    color: #6A983C;
    margin-bottom: 8px;
  }
  .banner__title {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 22px;
    color: #151515;
  }
  .banner__link {
    position: absolute;
    bottom: 32px;
    font-family: 'Poppins', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: #151515;
    border: 2px solid #92C064;
    border-radius: 12px;
    background: none;
    transition: 0.3s;
    padding: 12px 16px;
  }
  .banner__link * {
    transition: 0.3s;
  }
  .banner__link svg {
    margin-left: 13px;
  }
  .banner__link:hover,
  .banner__link:focus-visible {
    color: #fff;
    background: #92C064;
  }
  .banner__link:hover svg path,
  .banner__link:focus-visible svg path {
    stroke: #fff;
  }
</style>