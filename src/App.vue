<template>
<button @click="start" :disabled="isPlaying" class="btn_start">Start</button>
<Block v-if="isPlaying" :delay="delay" @result="results" />
<Result :time="time" v-if="showResult"/>
</template>

<script>
import Block from "./components/Block"
import Result from './components/Result'

export default {
  name: 'App',
  components:{Block,Result},
  data(){
    return{
      isPlaying:false,
      delay:0,
      time:0,
      showResult:false
    }
  },
  methods:{
    start(){
      this.delay = Math.floor(2000 + Math.random() * 5000)
    this.isPlaying=true
    this.showResult = false;
    },
    results(t){
    
     
      this.time=t;
       this.showResult = true;
       this.isPlaying =false
    }
  }

}
</script>

<style>
body{
  background:#333;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn_start{
  background:#0faf87;
  color:#fff;
  border:none;
  padding:8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin:10px
}
.btn_start:disabled{
  opacity: 0.2;
  cursor:not-allowed;
}
</style>
