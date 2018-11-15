<template>
  <div class="mainContainer">
    <h1>¡VueJS 2.0!</h1>
    
    <div>
      <img src="./assets/logo.png" alt="VueJS Logo">
    </div>
    
    <h1>
      <html-clock>
      </html-clock>
    </h1>
    
  </div>
</template>

<script>
  import HTMLClock from "./components/HTMLClock";
  
  export default {
    components: {
      'html-clock': HTMLClock
    }
  }
</script>


<style>
  .mainContainer {
    display: flex;
    flex-direction: column;
    
    justify-content: center;
    align-items: center;
  }
  
  h1 {
    font-family: Montserrat, Impact, sans-serif;
    font-size: 72px;
  }
</style>
