<template>
  <div id="app">
    <CubeCalculator />
  </div>
</template>

<script>
import CubeCalculator from "./components/CubeCalculator.vue";


// Bootstrap for Styling
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";


export default {
  name: "App",
  components: {
    CubeCalculator,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 100px 80px;
}

body {
  background-color: #2c3e50;
}
</style>
