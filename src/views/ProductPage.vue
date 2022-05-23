<script setup>
import axios from 'axios';
 import { reactive, watch } from '@vue/runtime-core';
const products = reactive({
    data: {}
})
axios.get('https://fakestoreapi.com/products/1')
    .then(response => products.data = response.data)
</script>

<template>
<div><p>{{products.data.description}}</p></div>
<div class="flex justify-end">
<div class="bg-[#E5DFA0] h-[812px] w-[193px]">
    <img :src="products.data.image" alt="">
</div>
</div>
</template>
