<template>
  <main>
    <search-main />
    <weather-main />
  </main>
</template>

<script>
import searchMain from "./searchMain.vue";
import weatherMain from "./weatherMain.vue";

export default {
  components: {
    searchMain,
    weatherMain,
  },
};
</script>

<style scoped>
main {
  width: 100%;
  margin: 25px auto;
}
</style>
