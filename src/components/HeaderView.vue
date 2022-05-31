<template>
    <div class="flex justify-between w-[100%] pt-[45px] pb-[40px] px-[25px]">
        <div id="sidebar" class="top-0 left-0 bg-slate-100 absolute w-0"></div>
        <div class="flex justify-center cursor-pointer" @click="openNav()"><img src="src/assets/menu.svg" alt="menu"></div>
        <div><h1 class="text-[#E5DFA0] text-[18px] font-normal">BRAND BENEFITS</h1></div>
        <div><img src="src/assets/search.svg" alt="search"></div>
    </div>
</template>
<script>
    function openNav() {
        console.log("Sidebar is opened");
        document.getElementById("sidebar").style.width = "200px";
    }
</script>
<style>
</style>
