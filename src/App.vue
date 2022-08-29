<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar/>
    </div>
    <div class="column is-three-quarter">
      <FormTacker @toSaveTask="saveTask" />
      <article class="list">
        <TaskDone v-for="(task, index) in tasks" :key="index" :task="task"/>
      </article>
    </div>


  </main>
</template>

<script lang="ts">

import { defineComponent } from 'vue';


import SideBar from './components/SideBar.vue'
import FormTacker from './components/FormTacker.vue'
import TaskDone from './components/TaskDone.vue';
import ITask from './interfaces/ITask'

export default defineComponent({
  name: 'App',
  // states from components
  data(){
    return{
      tasks: [] as ITask[]
    }
  },

  // Necessary to define which components this component has as childs
  components: {
    SideBar,
    FormTacker,
    TaskDone
  },
  // all methods from this components
  methods:{
    saveTask(task: ITask){
      this.tasks.push(task)
    }
  }
});
</script>

<style>
  .list{
    padding: 1.25rem;
    /* margin: 10px; */
  }

</style>
