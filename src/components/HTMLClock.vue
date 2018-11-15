<template>
  <div class="html-clock">
    <div class="hours">{{ hours }}</div>
    <div class="sep">:</div>
    <div class="minutes">{{ minutes }}</div>
    <div class="sep">:</div>
    <div class="seconds">{{ seconds }}</div>
  </div>
</template>

<script>
  import {setInterval} from 'timers';
  
  export default {
    props: ['theme'],
    data: function() { 
      return {
        hours: '--',
        minutes: '--',
        seconds: '--'
      } 
    },
    methods: {
      setHour() {
        this.hours = new Date().getHours();
      },
    
      setMinutes() {
        this.minutes = new Date().getMinutes();
      },
    
      setSeconds() {
        this.seconds = new Date().getSeconds().toString().padStart(2,'0');
      }
    },
    computed: {
      
    }, // cache functions
    watch: {
      
    },  // similar to state
    
    mounted() {
      setInterval( () => {
        this.setHour();
        this.setMinutes();
        this.setSeconds();    
      }, 1000);
    }
  }
  
</script>

<style lang="postcss" scoped>
  .html-clock {
    display: grid;
    grid-template-columns: 3fr 1fr 3fr 1fr 3fr 1.5fr;
    width: 500px;
    height: 125px;
  }
  
  .html-clock > div {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .sep {
    animation: papasitoBlink 1s linear infinite;
  }
  
  @keyframes papasitoBlink {
    0%,
    49% { opacity: 1; }
    
    50%,
    100% { opacity: 0; }
  }
  
  .red-lcd {
    color: red;
  }
  
  .green-lcd {
    color: green;
  }
  
  .yellow-lcd {
    color: yellow;
  }
</style>


