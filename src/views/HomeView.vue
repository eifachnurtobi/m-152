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
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
                {src: "/src/assets/logo.svg", alt: "Vue logo"},
            ]'>
        </ImageGallery>
        </div>
    </div>
</template>
<script setup lang="ts">
import ImageGallery from '@/components/ImageGallery.vue';
import Video from '../components/Video.vue';
</script>