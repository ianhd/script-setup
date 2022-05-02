<script>
import jokes from "@/assets/jokes.json";

export default {
    data() {
        return {
            jokeIdx: 0,
            joke: ``,
        };
    },
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
        this.joke = jokes[this.jokeIdx];
    },
};
</script>

<template>
    <div>
        <div v-html="jokeWithLineBreaks"></div>
        <button @click.prevent="refresh">Refresh</button>
    </div>
</template>
