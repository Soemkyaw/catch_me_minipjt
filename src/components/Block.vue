<template>
    <div class="block" v-if="showBlock" v-on:click="stopTimer">
        Click here
    </div>
</template>

<script>
export default {
    name,
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            score: 0,
            timer: null,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.score += 50;
                
            }, 50);
        },
        stopTimer() {
            clearInterval(this.timer);
            this.$emit("endGame",this.score)
            // this.showBlock = false;
        }
    },
}
</script>

<style>
.block{
  margin: 40px auto;
  width: 400px;
  background-color: aqua;
  padding-top: 30px;
  height: 400px;
}
</style>