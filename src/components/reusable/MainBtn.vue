<template>
  <button class="main__btn">
    {{ name }}
    <svg width="6" height="9" viewBox="0 0 6 9" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M1.5332 7.68663L4.2732 4.94663C4.39737 4.82172 4.46706 4.65276 4.46706 4.47663C4.46706 4.30051 4.39737 4.13154 4.2732 4.00663L1.60654 1.33997" stroke="#6A983C" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="bevel"/>
    </svg>
  </button>
</template>
<script>
  export default {
    props: {
      name: {
        type: String
      }
    }
  }
</script>
<style scoped>
.main__btn {
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
.main__btn svg {
  margin-left: 13px;
}
.main__btn:hover,
.main__btn:focus-visible {
  color: #6A983C;
}
</style>