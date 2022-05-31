<script setup>
import axios from 'axios';
import { RouterLink, RouterView } from 'vue-router'
import { reactive, watch } from '@vue/runtime-core';
import Footer from "./components/Footer.vue"
import Footer1 from "./components/Footer.vue"
const products = reactive({
    data: {}
})
axios.get('https://fakestoreapi.com/products')
    .then(response => products.data = response.data)
    console.log(products)
</script>

<template>
  <RouterView />
  <Footer/>
</template>

<style>

</style>
