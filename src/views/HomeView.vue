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
          <div class="shadow-2xl p-2 bg-white">
            <figure>
              <img :src="product.get_thumbnail" alt="">
            </figure>
            <h3 class="text-center">{{ product.name }}</h3>
            <p class="text-center"> {{ product.price }}</p>
            <p class="text-center">View details</p>          
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
