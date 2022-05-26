<template>
    <img :src="item.image" alt="" class="w-[100px] h-auto absolute z-10 bottom-[57px] left-[25px]">
    <div class="w-[150px] h-[150px] bg-[#E5DFA0] absolute bottom-0 flex items-end justify-center">
        <p class="z-20 mb-[7px] text-black text-[10px] leading-[13px] font-[Acme] text-center w-[100px]">{{item.title}}</p>
    </div>
</template>

<script>
export default {
    props: ["item"]
}
</script>