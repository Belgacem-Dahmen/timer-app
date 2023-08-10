<template>
    <p>Reaction Time = {{ score }} Ms</p>
    <p class="rank"> {{ rank }}</p>
  </template>
  
  
  
  <script>
  
  export default {
    props : ['score'],
    data() {
      return {
          rank:""  
  
      }
    },
    mounted () {
        if( this.score >250 ){
            this.rank="My grandMa can do better than you .."
        } else {
            this.rank= "You are a Ninja!!!"
        }
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
    .rank{
        font-size: 1.4em;
        color : #0faf87;
        font-weight: bold;
    }
</style>
  
  