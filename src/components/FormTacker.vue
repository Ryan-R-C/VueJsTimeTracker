<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
        <input type="text" class="input" name="" id="task" placeholder="Qual tarefa deseja iniciar"/>
      </div>
      <MainTimer />
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
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  


  
</style>
