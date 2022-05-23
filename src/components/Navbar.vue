<template>
  <nav class="w-full h-16 hidden lg:flex p-4 justify-between">
    <div class="h-auto w-auto">
      <router-link to="/">
        <p class="text-lg text-black ">Shop</p>
        </router-link>
    </div>
    <div>
    </div>
    <div class="h-auto w-auto">
      <router-link class="p-2 text-lg text-black" to="/summer">Summer</router-link>
      <router-link class="p-2 text-lg text-black" to="/winter">Winter</router-link>
      <router-link class="p-2 mx-2 bg-green-600 rounded-md text-white" to="/login">Login</router-link>
      <router-link class="p-2 mx-2 bg-blue-700 rounded-md text-white" to="/cart">
        <box-icon class="align-middle" name='cart' color="#FFF"></box-icon>
      </router-link>
    </div>
  </nav>
</template>

<script>
export default {

}
</script>

<style>

</style>