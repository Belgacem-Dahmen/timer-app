<template>
  <button @click="start" :disabled="isPlaying"> start Game </button>
  <Block v-if="isPlaying" :delay="delay" @endGame="warriResult" />
  <div >
    <Result v-if="showResult" :score="score" />
  </div>
  
  <button v-if="isPlaying" @click="quit"> Quit Game </button>
  
    
  

  
</template>



<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
export default {
  
  components: {
   Block,
   Result
  },
 
  data() {
    return {
      isPlaying : false,
      delay : null,
      showResult:false,
      score:null

    }
  },
  methods: {
      start(){
        this.isPlaying = true
        this.delay = 2000 + Math.random() * 5000
        
      },
      quit(){
        this.showResult = false
        this.isPlaying = false
      },
      warriResult(time){
        console.log(time)
        this.score = time;
        this.showResult = true;
        
        
      }
  }

}




</script>




