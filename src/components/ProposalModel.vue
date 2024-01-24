<template>
    <div class="absolute top-1/4 left-1/2 w-screen flex flex-col text-center items-center transform -translate-x-1/2">
        <h2 class="mb-6 mx-0 px-0 font-bold text-4xl">Wants to date me?</h2>
        <div>
            <button class="mr-10 bg-pink-500 text-white font-semibold py-2 px-4 rounded hover:bg-purple-700 transition duration-300 ease-in-out transform hover:scale-105" type="button" >YAS!</button>
            <button @mouseover="randomizePos" @click="randomizePos" :style="btnStyle" class="bg-red-500 text-white font-semibold py-2 px-4 rounded z-20" type="button">no</button>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    let btnStyle = ref({});

    const randomizePos = () => {
        btnStyle.value = {
            position: 'absolute',
            top: `calc(${Math.random()} * (100% - 45px))`,
            left: `calc(${Math.random()} * (100% - 45px))`
        }
    };
</script>