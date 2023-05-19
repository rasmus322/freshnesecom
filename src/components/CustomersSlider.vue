<template>
  <div class="customers__container container">
    <div class="customers__top">
      <h2 class="customers__title">
        Our customers says
      </h2>
      <button class="customers__btn">
        Go to all reviews 
        <svg width="6" height="9" viewBox="0 0 6 9" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1.5332 7.68663L4.2732 4.94663C4.39737 4.82172 4.46706 4.65276 4.46706 4.47663C4.46706 4.30051 4.39737 4.13154 4.2732 4.00663L1.60654 1.33997" stroke="#6A983C" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="bevel"/>
        </svg>
      </button>
    </div>
    <Flicking class="customers__slider" :options="{ align: 'center', circular: false, panelsPerView: 3 }" :plugins="plugins">
      <div v-for="customer in customers" :key="customer.id" class="customer__review">
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

  export default {
    components: {
      Flicking: Flicking
    },
    data() {
      return {
        customers: [
          {
            id: 1,
            name: 'Maria',
            surname: 'Nasdasodas',
            comment: `“ This is an super space for your customers qoute. Don’t worry it works smooth as pie. You will get all what you need by writiing a text here “`
          },
          {
            id: 2,
            name: 'Joe',
            surname: 'Qqwerty',
            comment: `“ Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ullam dolorum explicabo alias placeat. “`
          },
          {
            id: 3,
            name: 'Mike',
            surname: 'Shmit',
            comment: `“ This is an super space for your customers qoute. Don’t worry it works smooth as pie. You will get all what you need by writiing a text here “`
          },
          {
            id: 4,
            name: 'John',
            surname: 'zxc',
            comment: `“ This is an super space for your customers qoute. Don’t worry it works smooth as pie. You will get all what you need by writiing a text here “`
          }
        ],
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
  .customers__btn {
    font-family: 'Poppins', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: #151515;
    background: none;
    border: none;
    transition: 0.3s;
    cursor: pointer;
    padding: 6px 12px;
    margin-right: 0;
  }
  .customers__btn svg {
    margin-left: 13px;
  }
  .customers__btn:hover,
  .customers__btn:focus-visible {
    color: #6A983C;
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