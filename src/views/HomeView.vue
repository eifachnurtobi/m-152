<template>
    <h1 class="text-xl text-center">Tobi's Modul 152 Projekt</h1>
    <div class="p-8 text-center">
        <h2 class="text-lg">Video</h2>
        <Video class="mt-2 mb-8"></Video>

        <h2 class="text-lg mt-8 mb-2">Bildergallerie</h2>
        <div class="block">
            <ImageGallery
            class="m-auto" 
            :width="700"
            :height="500"
            :images='[
                {src: "https://picsum.photos/200/300", alt: "Vue logo"},
                {src: "https://picsum.photos/800/100", alt: "Vue logo"},
                {src: "https://picsum.photos/200/400", alt: "Vue logo"},
                {src: "https://picsum.photos/300/300", alt: "Vue logo"},
                {src: "https://picsum.photos/192/108", alt: "Vue logo"},
                {src: "https://picsum.photos/1600/900", alt: "Vue logo"},
            ]'>
        </ImageGallery>
        </div>

        <h2 class="text-lg mt-8 mb-2">Animation</h2>
        <div class="relative w-1/2 h-96 mx-auto">
            <Animation/>
        </div>
    </div>
</template>
<script setup lang="ts">
import ImageGallery from '@/components/ImageGallery.vue';
import Video from '../components/Video.vue';
import Animation from '../components/Animation.vue';
</script>