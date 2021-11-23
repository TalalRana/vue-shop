<template>
  <div id="app">
<!--    <img alt="Vue logo" src="./assets/logo.png">-->
    <AddProduct></AddProduct>
    <Products></Products>
  </div>
</template>

<script>
import Products  from './components/Products.vue'
import AddProduct from "@/components/AddProduct";

export default {
  name: 'App',
  components: {
    Products,
    AddProduct
  }
}
</script>

<style>
*,
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #2c3e50;
  padding-top: 30px;
}
#app {
  max-width: 700px;
  margin: 0 auto;
}
</style>
