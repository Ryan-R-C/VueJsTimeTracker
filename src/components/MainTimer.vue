<template>
    <div class="column">
        <div class="is-flex is-align-items-center is-justify-content-space-between">

            <!-- Such as ReactJs, vue has a props inside its components, to declare the params it is just necessary to type -> :selectedParam="value" -->
            <CountdownTimer :timeInSeconds="timeInSeconds" />

            <!-- When this button is clicked the function inside @click will be called -->
            <button class="button" @click="initiate" :disabled="isRunning">
                <span class="icon">
                    <i class="fas fa-play">
                    </i>
                </span>
                <span>
                    start
                </span>
            </button>
            <!-- To link a html prop with a state?
            declare the props with : like        V  -->
            <button class="button" @click="end" :disabled="!isRunning">
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
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CountdownTimer  from './CountdownTimer.vue'

export default defineComponent({
  name: 'MainTimer',
  components: {
    CountdownTimer
  },

  // to emit events to child components
  emits:['finish-countdown-timer'],

  // the initial state is defined here
  data(){
    // this return is always necessary!
    return {
      timeInSeconds: 0,
      timeTracker: 0 ,
      isRunning: false,

    }

  },


  // all methods used in this components are difined here
  methods: {
    initiate(){

      this.isRunning = true
      
      // 1s == 1000ms
      this.timeTracker = setInterval(
        () => {
          this.timeInSeconds += 1
        },
        1000
      )
    },
    end(){

      this.isRunning = false

      clearInterval(this.timeTracker)

      //$emit(method, payload)
      this.$emit('finish-countdown-timer', this.timeInSeconds)
      this.timeInSeconds = 0
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

