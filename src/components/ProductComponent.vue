<template>
    <div class="bg-[#E5DFA0] h-[150px] flex flex-col items-center justify-center">
        <img :src="item.image" alt="" class="-mt-10 w-[100px] h-80 z-10">
        <p class="text-black font-[Acme] text-center p-4">{{item.title}}</p>
    </div>
</template>

<script>
export default {
    props: ["item"]
}
</script>