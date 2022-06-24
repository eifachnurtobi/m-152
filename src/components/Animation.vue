<template>
    <div class="w-full h-full p-8">
        <div class="relative w-full h-full ">
            <IconAnimation 
                class="absolute h-10 w-10 -ml-5 -mt-5 transition-all ease-in-out duration-700"
                :style="positions[position]"
            />
        </div>
    </div>
</template>
<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue';
import IconAnimation from './icons/IconAnimation.vue';

const positions = ref([
    {top: 0, left: 0},
    {top: 0, left: '100%'},
    {top: '100%', left: '100%'},
    {top: '100%', left: 0},
]);

const position = ref(0);
const timer = ref();

onMounted(() => {
    timer.value = setInterval(() => {
        position.value = (position.value + 1)%positions.value.length;
    }, 1000);
})

onUnmounted(() => {
    clearInterval(timer.value);
})
</script>