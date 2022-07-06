<template>
  <main>
    <search-main />
  </main>
</template>

<script>
import searchMain from "./searchMain.vue";

export default {
  components: {
    searchMain,
  },
};
</script>

<style scoped>
main {
  width: 100%;
  margin: 25px auto;
}
</style>
