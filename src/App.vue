<script setup>
import axios from 'axios';
import { RouterLink, RouterView } from 'vue-router'
 import { reactive, watch } from '@vue/runtime-core';
const products = reactive({
    data: {}
})
axios.get('https://fakestoreapi.com/products')
    .then(response => products.data = response.data)
    console.log(products)
</script>

<template>
  <RouterView />
</template>

<style>
@import '@/assets/base.css';
</style>
