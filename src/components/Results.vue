<template>
    <p>Reaction Time: {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props: [
        'score'
    ],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = 'ninja fingers'
        } else if (this.score < 400) {
            this.rank = 'rapid reflexes'
        } else {
            this.rank = 'slowpoke'
        }
    }
}
</script>

<style>
    .rank {
        color: tomato;
        font-weight: bold;
    }
</style>