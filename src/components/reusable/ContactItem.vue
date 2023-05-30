<template>
  <ul class="contact__list">
    <h2 class="contact__title">
      {{ title }}
    </h2>
    <li v-for="item in items" :key="item.id" class="contact__item">
      <a :href="item.link" class="contact__link">
        {{ item.name }}
      </a>
    </li>
  </ul>
</template>
<script>
  export default {
    props: {
      title: {
        type: String
      },
      items: {
        type: Array,
      }
    }
  }
</script>
<style scoped>
</style>