<template>
<div class="result">
  <h2>the result</h2>
  <p>{{formatTime}}:MS</p>
  
  </div>
</template>

<script>
export default {
    props:['time'],
data(){
  return{
    formatTime:null
  }
},
mounted(){
this.formatTime = this.$props.time/60*100;
  console.log(this.formatTime)
}
}
</script>

<style>

</style>