<script setup>
import { ref, computed, onMounted } from "vue"
import jokes from "@/assets/jokes.json"
import MyConfetti from '@/components/MyConfetti.vue'

// perks: less indentation, less "this", root-level vars/methods

const jokeIdx = ref(0)
const joke = ref(``)

const refresh = () => {
    jokeIdx.value--;
    if (jokeIdx.value == -1) {
        // start over
        jokeIdx.value = jokes.length - 1;
    }
    joke.value = jokes[jokeIdx.value];
}

const jokeWithLineBreaks = computed(() => joke.value.replaceAll(`\n`, `<br/>`))

onMounted(() => {
    jokeIdx.value = jokes.length-1
    joke.value = jokes[jokeIdx.value];
})
</script>

<template>
    <div>
        <div v-html="jokeWithLineBreaks" class="j"></div>
        <div class="d-flex">
            <button @click.prevent="refresh">Refresh</button>
            <MyConfetti class="ml-auto"></MyConfetti>
        </div>
    </div>
</template>
