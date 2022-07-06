<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import Header from "./components/appHeader.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #f2f2f2;
  color: #2c3e50;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  font-weight: 400;
}
</style>
