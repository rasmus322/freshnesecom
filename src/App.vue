<template>
  <div>
    <CategoryMenu/>
    <SellingMenu/>
    <CustomersSlider/>
  </div>
</template>

<script>
import CategoryMenu from './components/CategoryMenu.vue';
import SellingMenu from './components/SellingMenu.vue';
import CustomersSlider from './components/CustomersSlider.vue';

export default {
    name: "App",
    components: { CategoryMenu, SellingMenu, CustomersSlider }
}
</script>

<style>

</style>
