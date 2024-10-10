<template>
  <div class="block" v-if="showBlock">
    <h2>Click me</h2>
  </div>
</template>

<script>
export default {
props:['delay'],
data(){
    return{
        showBlock : false
    }
},
mounted(){
    console.log("component mounted")

    setTimeout(()=>{
    this.showBlock = true 
    }, this.delay)
},
updated(){
    console.log("component updated !")
},
methods:{
    show(){
        
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