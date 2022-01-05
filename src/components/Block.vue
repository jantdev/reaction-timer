<template>
  <div class="block" v-if="showBlock"  @click="stopTimer">clik me</div>
</template>

<script>
export default {
name:'Block',
props:{
  delay:Number
},
data(){
  return{
    timer:0,
    setIntervalTimer:null,
    showBlock:false
  }
},

methods:{
 startTimer(){
  this.setIntervalTimer = setInterval(() => {
     this.timer = this.timer+10;
   }, 10);
 },
  stopTimer(){
   
    this.$emit('result',this.timer)
    clearInterval(this.setIntervalTimer)

  }
},
mounted(){
   
  setTimeout(()=>{
   this.showBlock =true;
  this.startTimer()
  },this.$props.delay)  
}
}
</script>

<style>
.block{
    width:400px;
    border-radius: 20px;
    background:#0faf87;
    color:#fff;
    text-align: center;
    padding:100px 0;
    margin:40px auto;
   
}

</style>