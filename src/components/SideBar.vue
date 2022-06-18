<template>
  <header>
    <img src="https://icons-for-free.com/download-icon-stopwatch+time+timer+icon-1320166029523848795_512.png" alt=""/> 
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'SideBar'
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  header {
      background-image: linear-gradient(to bottom, #0D0221 , #2E2157);
      width: 100%;
      height: 100vh;
  }

  /*
  img{
    max-width: 300px
  }
  
  
  */



  @media screen and (max-width: 420px){
    header {
      padding: 2.5rem;
      height: auto
    }
  }
  
</style>
