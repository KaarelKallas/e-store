<template>
    <img :src="item.image" alt="" class="w-24 h-auto absolute z-10 bottom-[40px] left-[25px]">
    <div class="w-[150px] h-[150px] bg-[#E5DFA0] absolute bottom-0">
    
    </div>
</template>

<script>
export default {
    props: ["item"]
}
</script>