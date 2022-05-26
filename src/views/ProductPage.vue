<script>
export default {
  data() {
    return {
      picked: 'One'
    }
  }
}
</script>
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
<p class="w-[132px] text-[#FFEADC] text-[15px]">{{products.data.title}}</p>
<p class="mt-[73px] text-[#FFEADC] text-[18px]">VÄNDA KAAREL OÜ</p>
<p class="mt-[27px] w-[132px] text-[#FFEADC] text-[15px]">{{products.data.description}}</p>
	<input type="radio" id="one" value="One" v-model="picked" />
	<label class="text-[15px] text-[#FFEADC]" for="one">M</label>
	<input type="radio" id="two" value="Two" v-model="picked" />
	<label class="text-[15px] text-[#FFEADC]" for="two">L</label>
<p class="text-[25px] mt-[52px] text-[#FFEADC]">{{products.data.price}}$</p>
<button class="mt-[36px] bg-[#E5DFA0] text-[#000000] text-[15px] w-[114px] h-[40px]">BUY NOW</button>
</div>
</div>
<div class="flex flex-col items-center bg-[#E5DFA0] h-[812px] w-[193px]">
    <img src="../assets/heart.svg" alt="">
    <img src="../assets/shopping-cart.svg" alt="">
    <img :src="products.data.image" alt="">
</div>
</div>
</template>
