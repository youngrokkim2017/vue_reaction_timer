<template>
    <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    // Add lifecycle methods
    mounted() { // only fires when mounted on page
        // console.log("component is mounted")
        // start the timer when its mounted
        setTimeout(() => {
            this.showBlock = true
            // console.log(this.delay)
            this.startTimer()
        }, this.delay)
    },
    // updated() { // only fires when updated
    //     console.log("component updated")
    // },
    // unmounted() {
    //     console.log("component unmounted")
    // },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTime)
        }
    }
}
</script>

<style>
    .block {
        width: 400px;
        border-radius: 20px;
        background: turquoise;
        color: white;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>