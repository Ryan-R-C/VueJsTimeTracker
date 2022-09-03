<template>
  <div class="box form">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input
        type="text"
        class="input"
        name=""
        id="task"
        placeholder="Qual tarefa deseja iniciar"
        v-model="description"
        />
      </div>
      <MainTimer @finish-countdown-timer="submitTask" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import MainTimer  from './MainTimer.vue'

export default defineComponent({
  name: 'FormTacker',
  components: {
    MainTimer
  },
  // returns a value to main component
  emits:[
    'toSaveTask'
  ],
  data(){
    return{
      description: ''
    }
  },
  methods:{
    submitTask(pastTime: number): void{

      this.$emit('toSaveTask', {
        timeInSeconds:pastTime,
        description:this.description,
      })

      this.description = ""

    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  
  .form {
    background-color: var(--primary-bg);
    color: var(--primary-text);
    transition: var(--main-transition);
  }

  
</style>
