<template>
    <div class="row product-container ">
        <app-product v-for="product in productList" :key="product" class="">
            <div class="card-header">
                <img class="card-img-top" :src="product.selectedImage" :alt="product.title">
                <h5 class="card-title">{{product.title}}</h5>
            </div>
            <div class="card-body">
                <small><strong>Count : </strong> {{product.count}}</small>
                <br>
                <small><strong>Price : </strong> {{product.price}}</small>
                <br>
                <small class="text-danger"><strong>Total : </strong> {{product.total}}</small>
            </div>  
        </app-product>
    </div>
</template>

<script>
import { eventBus } from '../main'

import Product from "./product.vue"
export default {
    components : {
        appProduct : Product
    },
    data(){
        return{
            productList: [],
            }
        },
    created(){
        eventBus.$on("productAdded",(product)=>{
            if(this.productList.length <10){
                this.productList.push(product)
                console.log(this.productList)
                eventBus.$emit("progressUpdated",this.productList.length)
            }else{
                alert("You cannot add any other Products!")
            }
            
            
        })
    }
    }
    

</script>