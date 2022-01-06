<template>
<div class="result">
  <h2>The Result</h2>
  <p>{{formatTime}} :MS</p>
  <p>Rang: {{rang}}</p>
  </div>
</template>

<script>
export default {
  name:'Result',
    props:['time'],
data(){
  return{
    formatTime:null,
    
    rang:null
  }
},
mounted(){
this.formatTime = this.$props.time;
  if(this.$props.time<250){
    this.rang = 'Ninja'
  }else if(this.$props.time <400){
    this.rang = 'Shugon'
  }else {
    this.rang = 'Snal'
  }
}
}
</script>

<style>
.result{
  width:400px;
  margin:0 auto;
  background: rgb(123, 185, 94);
  font-size: 16px;
  color:white;
  padding:20px;
  border-radius: 10px;
}
</style>