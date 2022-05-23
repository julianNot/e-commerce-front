<template>
  <div class="h-10 w-full bg-stone-400 flex justify-between">
        <router-link class="mx-3 m-auto" to="/">Shop</router-link>
        <div class="space-x-2 mr-3">
            <router-link to="/Summer">Summer</router-link>
            <router-link to="/winter">Winter</router-link>
            <router-link class="p-2 bg-green-600 rounded-md text-white" to="/winter">Login</router-link>
            <router-link class="p-2 bg-blue-600 rounded-md" to="/cart">
                <box-icon class="relative" name='cart' color="#FFF">a</box-icon>
            </router-link>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>