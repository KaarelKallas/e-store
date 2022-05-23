<script setup>
import ProductComponent from '../components/ProductComponent.vue';
import axios from 'axios';
import { reactive, watch } from '@vue/runtime-core';

const products = reactive({
    data: {}
})

axios.get('https://fakestoreapi.com/products')
    .then(response => products.data = response.data)
</script>

<template>
<div class="grid grid-cols-2 gap-x-[100px] justify-items-center items-center">
    <div
    v-for="(item, index) in products.data"
    class="w-[150px] h-[250px]">
        <ProductComponent :item="item"/>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            item: {},
        }
    }
}
</script>