<template>
  <div class="container">
    <h1 class="text-center">PRODUCT ADDER APP</h1>
    <hr>
    <app-new-product />
    <br><br>
    <app-progress-bar /> 
    <br><br>    
    <app-products />

  </div>


</template>


<script>

import NewProductVue from './components/NewProduct.vue';
import ProgressBarVue from './components/ProgressBar.vue';
import ProductsVue from './components/Products.vue';

  export default {
    components: {
      appNewProduct: NewProductVue,
      appProgressBar: ProgressBarVue,
      appProducts: ProductsVue
    }
  }
</script>

<style>
  body {
    background-color: aliceblue;
    padding-top: 20px;
    padding-bottom: 20px;
  }

  .card{
    margin-right: 5px;
    margin-bottom: 5px;
  }

  .card:last-child{
    margin-right: 0px;
  }

  .col-md-2{
    max-width: 15.666667%!important;
  }

  .product-container{
    margin-left: 15px;
  }

</style>