<script setup>
import ProductComponent from '../components/ProductComponent.vue';
import axios from 'axios';
import { reactive, watch } from '@vue/runtime-core';
import Footer from "../components/Footer.vue";
import Header from "../components/HeaderView.vue";

const products = reactive({
    data: {}
})

axios.get('https://fakestoreapi.com/products')
    .then(response => products.data = response.data)
</script>

<template>
<Header />
<div class="grid grid-cols-2 justify-items-center px-6">
    <div class="mt-14">
        <div
        v-for="(item, index) in products.data.slice(0,6)"
        class="w-[150px] h-[254px]">
            <RouterLink :to="'/products/' + item.id" class="">
                <ProductComponent :item="item"/>
            </RouterLink>
        </div>
    </div>
    <div class="mt-32">
        <div
        v-for="(item, index) in products.data.slice(6,12)"
        class="w-[150px] h-[254px]">
            <RouterLink :to="'/products/' + item.id" class="">
                <ProductComponent :item="item"/>
            </RouterLink>
        </div>
    </div> 
</div>
<Footer />
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