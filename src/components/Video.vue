<template>
    <div>
        <div class="aspect-video">
            <iframe width="100%" height="100%" src="https://www.youtube.com/embed/R5C1KkcMuNc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>

        <h3 
            class="m-4 cursor-pointer"
            @click="sourcesVisible = !sourcesVisible"    
        >
            Quellenverzeichnis
            <IconDirectionRight v-if="!sourcesVisible" class="inline w-4 white"/>
            <IconDirectionDown v-if="sourcesVisible" class="inline w-4 white"/>
        </h3>
        <div 
            class="block pl-6 mb-6"
            :class="sourcesVisible ? '' : 'hidden'"
        >
                <a href="https://opensea.io/XCOPY">Bilder</a>
                <a href="https://www.youtube.com/watch?v=rm-8bKMUAiY">Lied</a>
                <a href="https://www.youtube.com/watch?v=7gms2OFRzSM">The best skateboarding clips</a>
                <a href="https://www.youtube.com/watch?v=0uGETVnkujA">The Ultimate Snowboarding Compilation</a>
                <a href="https://www.youtube.com/watch?v=1TJ08caetkw">Alaskan Playground w/ John Jackson</a>
                <a href="https://www.youtube.com/watch?v=ck_S2sMZkGk">Christian Haller World Record 2016</a>
                <a href="https://www.youtube.com/watch?v=eJmicmxGdkM">TV Static Background</a>
        </div>
    </div>
</template>
<style>
    a {
        display:block;
    }
</style>

<script setup lang="ts">
    import IconDirectionDown from './icons/IconDirectionDown.vue';
    import IconDirectionRight from './icons/IconDirectionRight.vue';
    import { ref } from 'vue';

    const sourcesVisible = ref(false);
</script>