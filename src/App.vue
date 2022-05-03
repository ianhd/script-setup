<script setup>
import JokeOptionsApi from '@/components/JokeOptionsApi.vue'
import JokeCompositionApi from '@/components/JokeCompositionApi.vue'
</script>

<template>
    <div class="img"><img class="lol" src="./assets/lol.svg" /></div>
    <div class="cols">
        <JokeOptionsApi />
        <JokeCompositionApi />
    </div>
</template>

<style>
@import './assets/base.css';
.cols { display:grid; grid-template-columns: 300px 300px; }
.cols >div:first-child { border-right: 2px solid #999; padding-right: 40px; }
.cols >div:last-child { padding-left: 40px; }
</style>
