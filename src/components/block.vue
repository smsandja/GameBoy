<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    <h2>Click me</h2>
  </div>
</template>

<script>
export default {
props:['delay'],
data(){
    return{
        showBlock : false,
        time: null,
        reactionTime: 0
    }
},
mounted(){
    console.log("component mounted")

    setTimeout(()=>{
    this.showBlock = true 
    this.startTimer()
    }, this.delay)
},
updated(){
    console.log("component updated !")
},
methods:{
    startTimer(){
       this.time = setInterval(() => {
            this.reactionTime += 10
        }, 10);
    },
    stopTimer(){
        clearInterval(this.time)
        this.$emit('end', this.reactionTime)
    }
}
}
</script>

<style scoped>
.block {
    width:400px;
    height: 200px;
    border-radius: 5px;
    padding: 10px 0px 10px 0px;
    margin: 10px auto;
    background: #3acaba;
    align-items: center;
}
</style>