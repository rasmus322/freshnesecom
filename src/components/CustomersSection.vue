<template>
  <div class="customers__container container">
    <div class="customers__top">
      <h2 class="customers__title">
        Our customers says
      </h2>
      <MainBtn :name="name"/>
    </div>
    <Flicking class="customers__slider" :options="{ align: 'center', circular: false, panelsPerView: 3 }" :plugins="plugins">
      <div v-for="customer in sliderCustomers" :key="customer.id" class="customer__review">
        <p class="customer__comment">
          {{ customer.comment }}
        </p>
        <h4 class="customer__name">
          {{ customer.name + ' ' + customer.surname }}
        </h4>
      </div>
    </Flicking>
  </div>
</template>
<script>
  import Flicking from "@egjs/vue3-flicking";
  import { Fade } from "@egjs/flicking-plugins";
  import MainBtn from "./reusable/MainBtn.vue";
  import customers from '../data/customers.js'

  export default {
    components: {
      Flicking: Flicking,
      MainBtn
    },
    data() {
      return {
        sliderCustomers: customers.splice(0, 5),
        name: 'Go to all reviews',
        plugins: [new Fade()]
      }
    }
  }
</script>
<style scoped>
  .customers__container {
    padding: 65px 0;
  }
  .customers__top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 45px;
  }
  .customers__title {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 18px;
    color: #151515;
    margin-left: 0;
  }
  .customers__slider {
    padding: 36px 0;
  }
  .customer__review {
    width: 369px;
    height: 198px;
    position: relative;
    outline: 1px solid #F1F1F1;
    border-radius: 12px;
    text-align: center;
    padding: 24px 0 40px 0;
    margin-right: 32px;
  }
  .customer__review:first-child::after {
    content: '';
    width: 48px;
    height: 48px;
    position: absolute;
    background: url('../../public/imgs/customers3.png');
    left: 45%;
    bottom: -24px;
  }
  .customer__review:nth-child(2)::after {
    content: '';
    width: 48px;
    height: 48px;
    position: absolute;
    background: url('../../public/imgs/customers.png');
    left: 45%;
    bottom: -24px;
  }
  .customer__review:nth-child(3)::after {
    content: '';
    width: 48px;
    height: 48px;
    position: absolute;
    background: url('../../public/imgs/customers2.png');
    left: 45%;
    bottom: -24px;
  }
  .customer__review:last-child::after {
    content: '';
    width: 48px;
    height: 48px;
    position: absolute;
    background: url('../../public/imgs/customers1.png');
    left: 45%;
    bottom: -24px;
  }
  .customer__comment {
    max-width: 300px;
    font-family: 'Poppins', sans-serif;
    font-weight: 500;
    font-size: 15px;
    color: #151515;
    line-height: 22.5px;
    margin-bottom: 24px;
  }
  .customer__name {
    font-family: 'Poppins', sans-serif;
    font-weight: 600;
    font-size: 12px;
    color: #a9a9a9;
  }
</style>