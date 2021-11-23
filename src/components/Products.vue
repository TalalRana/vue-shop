<template>
  <div>
    <h1>Products </h1>
    <ul class="products-listng">
      <li v-for="product in allProducts" :key="product.id" >
         <strong> {{product.id}} &nbsp; || {{product.title}}</strong> | &nbsp; &nbsp; {{product.price | currency }}
        <button @click="deleteProduct(product.id)"> X </button>
      </li>
    </ul>
    {{allProducts}}
  </div>
</template>

<script>
import { mapGetters, mapActions } from "vuex";
  export default {
    name: 'Products',
    filters: {
      currency: function (value){
        return "PKR" + parseFloat(value).toFixed(2);
      }
    },
    methods: {
      ...mapActions(["getProducts" , "deleteProduct"])
    },
    computed: mapGetters(["allProducts"]),
    created() {
      this.getProducts()
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>

</style>
