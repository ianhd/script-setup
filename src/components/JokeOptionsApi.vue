<script>
import jokes from '@/assets/jokes.json'

export default {
    data() {
        return {
            jokeIdx: 0,
            joke: ``
        }
    },
    methods: {
        next() {
            this.jokeIdx++
        },
    },
    mounted() {
        this.joke = jokes[this.jokeIdx]
    },    
};
</script>

<template>
    {{joke}}
</template>

<style scoped></style>
