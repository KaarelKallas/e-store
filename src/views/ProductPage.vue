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
const pagepath = window.location.pathname
axios.get('https://fakestoreapi.com' + pagepath)
    .then(response => products.data = response.data)
</script>
<template>
<div class="flex justify-end font-[Acme]">
  <div class="flex items-center">
    <div>
      <RouterLink to="/">
        <img src="../assets/chevron-left.svg" alt="Back">
      </RouterLink>
      <p class="w-[132px] text-[#FFEADC] text-[15px]">{{products.data.title}}</p>
      <p class="mt-[73px] text-[#FFEADC] text-[18px]">VÄNDA KAAREL OÜ</p>
      <p class="mt-[27px] w-[132px] text-[#FFEADC] text-[15px]">{{products.data.description}}</p>
      <form action="">
        <input type="radio" id="one" value="One" v-model="picked" @click="picked = 'One'"/>
        <label class="text-[15px] text-[#FFEADC]" for="one">M</label>
        <input type="radio" id="two" value="Two" v-model="picked" @click="picked = 'Two'" />
        <label class="text-[15px] text-[#FFEADC]" for="two">L</label>
      </form>
      <p v-if="picked == 'One'" class="text-[25px] mt-[52px] text-[#FFEADC]">{{products.data.price}}€</p>
      <p v-if="picked == 'Two'" class="text-[25px] mt-[52px] text-[#FFEADC]">{{products.data.price*2}}€</p>
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
