<template>
    <div class="block w-min">
        <div class="flex justify-center bg-stripes-gray border rounded-lg border-none p-4 w-fit">
            <!-- navigation -->
            <div class="absolute inset-x-0 top-1/2 translate-y-1/2 z-10">
                <div class="flex place-content-between">
                    <button @click="() => navigate(-1)">
                        <IconLeft class="stroke-white w-12 h-12"></IconLeft>
                    </button>
                    <button @click="() => navigate(+1)">
                        <IconRight class="stroke-white w-12 h-12"></IconRight>
                    </button>
                </div>
            </div>

            <!-- image gallery -->
            <div class="relative overflow-hidden" 
                :style="{
                    width: `${props.width}px`,
                    height: `${props.height}px`,
                }"
            >
                <div 
                    v-for="(image, index) in images" 
                    class="absolute inset-0 transition-all duration-500"
                    :class="getImageTranslate(index)"
                >
                    <img :src="image.src" :alt="image.alt"
                        class="h-full m-auto"
                    />
                </div>
            </div>
        </div>

        <!-- location indicator -->
        <div 
            class="inline-flex justify-center p-4"
            :style="{
                width: `${props.width}px`,
            }"
        >
            <div v-for="(image, index) in images" 
                class="w-4 h-4 mx-1 rounded-full border-white border-2"
                :class="index === currentImage ? 'bg-white' : 'bg-transparent'"
            ></div>
        </div>
    </div>
</template>

<style>
    .bg-stripes-gray {
        background-color: #9ca3af1a;
        background-image: linear-gradient(135deg,#6b728080 10%,transparent 0,transparent 50%,#6b728080 0,#6b728080 60%,transparent 0,transparent);
        background-size: 7.07px 7.07px;
    }
</style>

<script setup lang="ts">
    import { ref } from 'vue';
import IconLeft from './icons/IconLeft.vue';
import IconRight from './icons/IconRight.vue';

    interface Image {
        src: string;
        alt: string;
    }

    const props = defineProps({
        width: {
            type: Number,
            required:true,
        },
        height: {
            type: Number,
            required:true,
        },
        images: {
            type: Object as () => Image[],
            required: true,
        }
    })

    const currentImage = ref(0);

    const getImageTranslate = (imageIndex: Number) => {
        if(imageIndex === currentImage.value){
            return 'translate-x-0';
        }

        if(imageIndex < currentImage.value){
            return '-translate-x-full';
        }

        if(imageIndex > currentImage.value){
            return 'translate-x-full';
        }
    }

    const navigate = (direction: number) => {
        const newPosition = (currentImage.value + direction) % props.images.length;

        if(newPosition >= 0){
            currentImage.value = newPosition;
        }else{
            currentImage.value = props.images.length - 1;
        }
    }
</script>