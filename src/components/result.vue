<template>
  <div >
    <p>Reaction Time: {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
  </div>
</template>

<script>

export default {
  data(){
    return{
      rank: null
    }
  },
  props : ['score'],

  mounted(){
    if(this.score < 250){
      this.rank = "Ninja fingers"
    } else if(this.score < 400){
      this.rank = "Rapid reflexes"
    } else {
      this.rank = "suck ..."
    }
}

}

</script>

<style>
.rank{
  font-size: large;
  font-weight: bold;
  color: #0acaba;
}
</style>