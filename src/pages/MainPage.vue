<template>
  <div>
    <CategorySection/>
    <SellingSection/>
    <CustomersSection/>
    <SalesSection/>
  </div>
</template>
<script>
  import CategorySection from './../components/CategorySection.vue';
  import SellingSection from './../components/SellingSection.vue';
  import CustomersSection from './../components/CustomersSection.vue';
  import SalesSection from './../components/SalesSection.vue';

  export default {
    components: { CategorySection, SellingSection, CustomersSection, SalesSection }
  }
</script>
<style scoped>

</style>