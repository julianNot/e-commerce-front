import axios from 'axios';
<template>
    <div class="page-product mt-8">
        <div class="flex flex-row justify-start">
            <div class="w-3/5 flex flex-col justify-center items-center m-3">
                <figure class="">
                    <img :src="product.get_image" width="500" alt="">
                </figure>
                <h1 class="font-semibold text-xl text-left">{{ product.name }}</h1>
                <p class="text-left">{{ product.description }}</p>
            </div>
            <div class="w-2/5 m-3 flex justify-end ">
                <div class="space-y-3">
                    <h2 class="text-left">Information</h2>
                    <p><strong>Price: </strong>${{ product.price }}</p>
                    <div class="flex">
                        <input class="w-1/3 p-2" type="number" min="1" v-model="quantity">
                        <a href="" class="bg-green-600 p-2 rounded-md">Add to cart</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name : 'product',
    data(){
        return{
            product : {},
            quantity : 1,
        }
    },
    mounted() {
        this.getProduct()
    },
    methods: {
        getProduct(){
            const category_slug = this.$route.params.category_slug
            const product_slug = this.$route.params.product_slug

            axios.get(`api/v1/products/${category_slug}/${product_slug}`)
                .then(resp => {
                    this.product = resp.data
                }).catch(error => {
                    console.log(error);
                })
        }
    },
}
</script>

<style>

</style>