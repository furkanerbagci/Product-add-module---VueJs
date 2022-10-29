<template>
  <div class="container bg-ligth">
    <br>
    <h2 class="text-center text-warning">Product Add Module</h2>
    <hr>
    <app-new-product></app-new-product>
    <br>
    <app-progress></app-progress>
    <br>
    <h3 class="text-center text-warning">Added Product List</h3>
    <hr>
    <app-products></app-products>
  </div>


</template>

<script>

  import newProduct from "./components/newProduct.vue"
  import Products from "./components/products.vue"
  import Progress from "./components/progress.vue"
  export default {
    components : {
      appNewProduct : newProduct,
      appProducts : Products,
      appProgress : Progress
    }
  }
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
.container{
  height: 100vh;
}


  .card:last-child{
    margin-right: 0px;
  }



  .product-container{
    margin-left: 15px;
  }

</style>