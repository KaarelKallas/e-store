<script setup>
import axios from 'axios';
import { RouterLink, RouterView } from 'vue-router'
import { reactive, watch } from '@vue/runtime-core';
import ProductPage from "./views/ProductPage.vue"
const products = reactive({
    data: {}
})
</script>

<template>
  <RouterView />
</template>

<style>
@import '@/assets/base.css';
</style>
