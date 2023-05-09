<template>
    <div class="block" v-if="showBlock" @click="endGame">Click Me</div>
</template>

<script>
export default {
    data(){
        return {
            showBlock : false,
            score : 0 ,
            timer : null
        }
    },
    props : [
        'delay'
    ],
    mounted(){
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay);
    },
    methods : {
        endGame(){
            this.$emit('endGame',this.score)
            this.showBlock = false
            clearInterval(this.timer)
        },
        startTimer(){
            this.timer = setInterval(() => {
                this.score += 50 
            }, 50);
        }
    }
}
</script>

<style>
.block {
    width: 250px;
    height: 150px;
    text-align: center;
    margin: 100px auto;
    padding: 50px;
    background-color: aqua;
}
</style>
