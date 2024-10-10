<template>
    <h1>{{ title }}</h1>
    <p>Do you want to play ?</p>
    <button class="startbutton" @click="start" :disabled="isPlaying">Start</button>
    <block v-if="isPlaying" :delay="delay"/>
</template>

<script>
import block from './components/block.vue';
import result from './components/result.vue';

export default {
  name: 'App',
  components: { result, block},
  data() {
    return {
      title: "Welcome to our Game Party",
      isPlaying : false,
      delay : null
    }
  },
  methods : {
    start(){
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
      console.log(this.delay)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.startbutton {
  padding: 10px;
  margin: 8px;
  background: #3acaba;
  border : 1px solid white;
  border-radius : 5px;
  color: white;
}

</style>
