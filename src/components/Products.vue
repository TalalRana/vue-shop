<template>
  <div>
    <table id="firstTable">
      <thead>
      <tr>
        <!--        <th>ID</th>-->
        <th>Product</th>
        <th>Price</th>
        <th>Action</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="product in allProducts" :key="product.id" >
        <!--        <td>{{product.id}}</td>-->
        <td>{{product.title}}</td>
        <td>{{product.price}}</td>
        <td>
          <button @click="deleteProduct(product.id)">❌</button>
        </td>
      </tr>
      </tbody>
    </table>
    <!--    <ul class="products-listng">-->
    <!--      <li v-for="product in allProducts" :key="product.id" >-->
    <!--         <strong> {{product.id}} &nbsp; | {{product.title}}</strong> | &nbsp; &nbsp; {{product.price | currency }}-->


    <!--      </li>-->
    <!--    </ul>-->
    <!--    {{allProducts}}-->
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
  .products-listing li {
    background: #fff;
    padding: 15px;
    border-radius: 5px;
    margin-bottom: 20px;
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .products-listing li button {
    background: #fff;
    border: 1px solid #fff;
    border-radius: 5px;
    color: #000;
    font-size: 16px;
    cursor: pointer;
  }
  table {
    font-family: 'Open Sans', sans-serif;
    width: 750px;
    border-collapse: collapse;
    border: 3px solid #44475C;
    margin: 10px 10px 0 10px;
  }

  table th {
    text-transform: uppercase;
    text-align: left;
    background: #44475C;
    color: #FFF;
    padding: 8px;
    min-width: 30px;
  }

  table td {
    text-align: left;
    padding: 8px;
    border-right: 2px solid #7D82A8;
  }
  table td:last-child {
    border-right: none;
  }
  table tbody tr:nth-child(2n) td {
    background: #D4D8F9;
  }

</style>
