<script setup>
import confetti from 'https://cdn.skypack.dev/canvas-confetti'

const dotheThing = () => {
    confetti()
}
</script>

<template>
    <div>
        <button @click.prevent="dotheThing">🎉</button>
    </div>
</template>
