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
<div class="flex gap-x-[30px] justify-center">
    <div>
        <div
        v-for="(item, index) in products.data.slice(0,6)"
        class="w-[150px] h-[254px]">
            <ProductComponent :item="item"/>
        </div>
    </div>
    <div class="mt-[75px]">
        <div
        v-for="(item, index) in products.data.slice(6,12)"
        class="w-[150px] h-[254px]">
            <ProductComponent :item="item"/>
        </div>
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