<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" name="" id="task" placeholder="Qual tarefa deseja iniciar"/>
      </div>
      <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">
          <section>
            <strong strong>{{ timePassed }}</strong>
          </section>
         <!-- When this button is clicked the function inside @click will be called --> 
        <button class="button" @click="initiate">
          <span class="icon">
            <i class="fas fa-play">
            </i>
          </span>
          <span>
            start
          </span>
        </button>

        <button class="button" @click="end">
          <span class="icon">
            <i class="fas fa-stop">
            </i>
          </span>
          <span>
            stop
          </span>
          
        </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'FormTacker',

  // the initial state is defined here
  data(){
    // this return is always necessary!
    return {
      timeInSeconds: 0,
      timeTracker: 0 

    }

  },

  computed: {// monitorate a information, if the information changes, it reacts 
    /*It is declared as a method, but used as a property*/
    timePassed () : string {
      // 0 => '00:00:00'
      // return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8)

      const timeInMilliseconds = this.timeInSeconds * 1000
      const timeInMillisecondsString = new Date(timeInMilliseconds).toISOString()


     return timeInMillisecondsString.substr(11, 8) // returns only HH:MM:SS
    }
  },


  // all methods used in this components are difined here
  methods: {
    initiate(){
      // 1s == 1000ms
      this.timeTracker = setInterval(
        () => {
          this.timeInSeconds += 1
        },
        1000
      )
    },
    end(){
      clearInterval(this.timeTracker)

    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  


  
</style>
