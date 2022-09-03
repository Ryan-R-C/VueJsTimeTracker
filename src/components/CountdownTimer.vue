<template>
  <section>
    <strong class="timer">{{ timePassed }}</strong>
  </section>
</template>


<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CountdownTimer',

  // the initial state is defined here
  
  //in props -> all recived values -> like ReactJs props or params in a function
  props:{
    timeInSeconds: {
        type: Number,
        default: 0,
    }

  },


  computed: {// monitorate a information, if the information changes, it reacts 
    /*It is declared as a method, but used as a property*/
    timePassed () : string {
      // 0 => '00:00:00'

      const timeInMilliseconds = this.timeInSeconds * 1000
      const timeInMillisecondsString = new Date(timeInMilliseconds).toISOString()


     return timeInMillisecondsString.substr(11, 8) // returns only HH:MM:SS
    }
  },

});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  

  .timer {
    /* background-color: var(--primary-bg); */
    color: var(--primary-text);
    transition: var(--main-transition);
  }

  
</style>
