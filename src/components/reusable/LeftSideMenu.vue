<template>
  <ul class="menu__list">
    <h2 class="menu__title">
      {{ title }}
    </h2>
    <li v-for="item in items" :key="item.id" class="menu__item">
      <a href="" class="menu__link">
        {{ item.name }}
      </a>
    </li>
    <a href="" class="menu__btn">
      {{ btn }}
      <svg width="7" height="10" viewBox="0 0 7 10" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M2.0332 8.18669L4.7732 5.44669C4.89737 5.32178 4.96706 5.15281 4.96706 4.97669C4.96706 4.80056 4.89737 4.63159 4.7732 4.50669L2.10654 1.84002" stroke="#151515" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="bevel"/>
      </svg>          
    </a>
  </ul>
</template>
<script>
  export default {
    props: {
      title: {
        type: String,
        required: true,
      },
      items: {
        type: Array,
        required: true,
      },
      btn: {
        type: String,
        required: true,
      }
    },
    data() {
      return {

      }
    }
  }
</script>
<style scoped>
.menu__list {
  width: 20%;
  height: 282px;
  position: relative;
  margin-right: 32px;
  margin-left: 0;
}
.menu__title {
  font-family: 'Poppins', sans-serif;
  font-weight: 600;
  font-size: 18px;
  color: #151515;
  margin-bottom: 16px;
}
.menu__item:not(:last-child) {
  margin-bottom: 12px;
}
.menu__link {
  font-family: 'Open Sans', sans-serif;
  font-weight: normal;
  font-size: 14px;
  color: #6A983C;
  text-decoration: underline;
}
.menu__btn {
  position: absolute;
  font-family: 'Poppins', sans-serif;
  font-weight: 700;
  font-size: 15px;
  color: #151515;
  background: #F5F5F5;
  border-radius: 12px;
  padding: 13px 16px;
  bottom: 0;
}
.menu__btn svg {
  margin-left: 6px;
}
</style>