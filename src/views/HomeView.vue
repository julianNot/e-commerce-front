<template>
  <div>
    <section class="h-1/2 w-full  inline-block bg-slate-500">
      <div class="text-center h-full w-full p-20">
        <p class="text-white text-3xl">Welcome to ShopDjango</p>
        <p class="text-white text-lg p-2">The best shop store online</p>
      </div>
    </section>
    <div>
      <div>
        <h2 class="text-black text-center p-4 text-2xl">Latest products</h2>
      </div>
      <section class="flex space-x-5 m-10">
        <div v-for="product in lastestProducts" :key="product.id">
          <div class="shadow-2xl p-4 bg-white">
            <figure>
              <img :src="product.get_thumbnail" alt="">
            </figure>
            <div class="flex flex-col justify-center items-center">
              <h3 class="text-center">{{ product.name }}</h3>
              <p class="text-center text-gray-600">$ {{ product.price }}</p>
              <router-link :to="product.get_absolute_url" class="p-2 m-1 bg-gray-700 text-white rounded-md">View details</router-link>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HomeView',
  data(){
    return {
      lastestProducts : []
    }
  },
  components: {

  },
  methods: {
    getLastestProducts(){
      axios.get('/api/v1/lastest-products/')
      .then(resp => {
        this.lastestProducts = resp.data
      })
      .catch(error => {
        console.log(error);
      })
    }
  },
  mounted() {
    this.getLastestProducts()
  },

}
</script>
