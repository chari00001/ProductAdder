<template>

    <div v-if="productList.length !== 0">
        <h3 class="text-center">List of products</h3>
        <hr>
        <div class="row product-container">
            <app-product v-for="product in productList">

            <img class="card-img-top" :src="product.selectedImage" :alt="product.title">
            <div class="card-body">
            <h5 class="card-title">{{ product.title }}</h5>
            <small><strong>Amount : </strong> {{ product.count }}</small>
            <br>
            <small><strong>Price : </strong> {{ product.price }}</small>
            <br>
            <small><strong>Total : </strong> {{ product.totalPrice }}</small>
            </div>

            </app-product>
        </div>
    </div>

</template>

<script>

import ProductVue from './Product.vue';
import {eventBus} from '../main';

export default {
    components: {
        appProduct: ProductVue
    },
    data(){
        return {
            productList: []
        }
    },
    created(){
        eventBus.$on("productAdded", (product) => {
            if (this.productList.length < 10) {
                this.productList.push(product);
                eventBus.$emit("progressBarUpdated", this.productList.length);
            }
            else {
                alert("You can't add more products")
            }
        });
    }
}

</script>