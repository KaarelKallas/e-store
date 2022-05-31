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
<div class="grid grid-cols-2 justify-center px-6">
    <div class="mt-14">
        <div
        v-for="(item, index) in products.data.slice(0,6)"
        class="w-[150px] h-[300px]">
            <RouterLink :to="'/products/' + item.id" class="">
                <ProductComponent :item="item"/>
            </RouterLink>
        </div>
    </div>
       <div class="mt-32 space-y-10">
            <div
            v-for="(item, index) in products.data.slice(6,12)"
            class="w-[150px] h-[254px]">
                <RouterLink :to="'/products/' + item.id" class="w-[150px] h-[254px]">
                    <ProductComponent :item="item"/>
                </RouterLink>
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