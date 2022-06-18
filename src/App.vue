<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar/>
    </div>
    <div class="column is-three-quarter">
      <FormTacker />
    </div>

  </main>
</template>

<script lang="ts">

import { defineComponent } from 'vue';


import SideBar from './components/SideBar.vue'
import FormTacker from './components/FormTacker.vue'


export default defineComponent({
  name: 'App',
  // Necessary to define which components this component has as childs
  components: {
    SideBar,
    FormTacker
  }
});
</script>

<style>

</style>
