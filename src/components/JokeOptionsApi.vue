<script>
import jokes from "@/assets/jokes.json"
import MyConfetti from '@/components/MyConfetti.vue'

export default {
    data() {
        return {
            jokeIdx: 0,
            joke: ``,
        };
    },   
    components: { MyConfetti },
    methods: {
        refresh() {
            this.jokeIdx++
            if (this.jokeIdx == jokes.length) { // start over
                this.jokeIdx = 0
            }
            this.joke = jokes[this.jokeIdx]
        },
    },
    computed: {
        jokeWithLineBreaks() {
            return this.joke.replaceAll(`\n`,`<br/>`)
        }
    },
    mounted() {
        this.joke = jokes[this.jokeIdx]
    },
};
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
