<template>
    <div v-if="showBlock" class="block" @click="stopTimer">
        <p> click Me when i appear</p>
        
    </div>
  </template>
  
  
  
  <script>
  
  export default {
    props : ['delay'],
    data() {
      return {
        showBlock:false,
        timer:null,
        reactionTime:null
  
      }
    },
    mounted () {
    setTimeout(() => {
      this.showBlock = true
      this.startTimer()
    },this.delay)
  }, 
    
    
    methods: {
       startTimer(){
        this.timer = setInterval( ()=> {
          this.reactionTime += 10
        } ,10)
       },
       stopTimer(){
        console.log(this.reactionTime)
        this.$emit('endGame', this.reactionTime)
        clearInterval(this.timer);
        this.showBlock = false;
        
        

    },
    
  
  }
}
  
  
  
  
  </script>
  
  
  <style>
    .block{
        width: 400px;
        border-radius: 20px;
        color: white;
        background: #0faf87;
        text-align: center;
        padding: 100px 0;
        margin: 40px 0;
    }
</style>
  
  