<template>
    <div v-if="showBlock" class="showBlock" @click="stop">
        <h1>ANOTHER GAME</h1>
    </div>

</template>

<script lang="ts">
export default {
    props: ['delay', 'isPlaying'],
    emits: ['end'],
    data() {
        return {
            showBlock: false,
            showBlock2: false,
            timer: 0,
            reactionTime: 0,

        }
    },
    mounted() { 
        setTimeout(() => {
            this.showBlock = true
            this.start()
        }, this.delay)
        
    },
    methods: {
        start() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        
        },
        stop() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
            console.log( this.reactionTime)
        },
        

    }
};

</script>

<style scoped>
/* MAKE LIKE A BOX */
</style>