<template>
  <header>
    <img src="https://alura-tracker.vercel.app/img/logo.0acd531c.png" alt=""/> 
    
    <button class="button" @click="toggleTheme">
      {{ themeButtonText }}
    </button>

  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'SideBar',

  data(){
    return{
      isDarkModeActive: false
    }
  },

  emits: ['toToggleTheme'],

  computed: {
    themeButtonText (){
      if(this.isDarkModeActive){
        return 'Desativar modo escuro'
      }

      return "Ativar modo escuro"
    }
  },

  methods: {
    toggleTheme () {
      this.isDarkModeActive = !this.isDarkModeActive
      
      this.$emit('toToggleTheme', this.isDarkModeActive)
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->


<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  background-image: linear-gradient(to bottom, #0d3b66 , #0b2e4f);
  width: 100%;
  height: 100vh;
  text-align: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
