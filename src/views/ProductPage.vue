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
<div class="flex justify-end">
<div class="flex items-center">
<div>
<p class="w-[132px] text-[#FFEADC] text-[15px]">{{products.data.description}}</p>
<p class="mt-[73px] text-[#FFEADC] text-[18px]">VÄNDA KAAREL OÜ</p>
<p class="mt-[27px] w-[132px] text-[#FFEADC] text-[15px]">{{products.data.description}}</p>
</div>
</div>
<div class="flex items-center bg-[#E5DFA0] h-[812px] w-[193px]">
    <img :src="products.data.image" alt="">
</div>
</div>
</template>
