<template>
  <main class="columns is-gapless is-multiline" :class="{ 'darkmode':isDarkModeActive }">
    <div class="column is-one-quarter">
      <SideBar @toToggleTheme="toggleTheme"/>
    </div>
    <div class="column is-three-quarter  content">
      <FormTacker @toSaveTask="saveTask" />
      <article class="list">
        <TaskDone v-for="(task, index) in tasks" :key="index" :task="task"/>
        
        <StyledBox v-if="isTasksEmpty">
          Você não está muito produtivo hoje...
        </StyledBox>
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
import StyledBox from './components/StyledBox.vue';

export default defineComponent({
  name: 'App',
  // states from components
  data(){
    return{
      tasks: [] as ITask[],
      isDarkModeActive: false,
    }
  },

  // Necessary to define which components this component has as childs
  components: {
    SideBar,
    FormTacker,
    TaskDone,
    StyledBox
},
  // all methods from this components
  methods:{
    saveTask(task: ITask){
      this.tasks.push(task)
    },
    toggleTheme(darkModeActive: boolean) {
      this.isDarkModeActive = !!darkModeActive

    }
  },

  computed: {
    isTasksEmpty (): boolean {
      return this.tasks.length === 0
    }
  }
});
</script>

<style>
  .list{
    padding: 1.25rem;
    /* margin: 10px; */
  }

  main {
    --primary-bg : #ffff;
    --primary-text : #363636;
    --main-transition: background-color 1.5s, color .75s;
  }


  main.darkmode {
    --primary-bg : #2b2d42;
    --primary-text : #ddd;
  }

  .content{
    background-color: var(--primary-bg);
    transition: background-color 1.5s, color .75s;
  } 

</style>
