<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->


  <div class="main">
    
    <NavigationComponent 
      @toggleDarkMode="toggleDarkMode"
    />

    <div class="container">
      <router-view />
    </div>
    
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import NavigationComponent from './components/NavigationComponent.vue'
export default defineComponent({

  // setup(){
  //   const theme = ref('')
  //   const targetTheme = ref('')

  //   return {theme, targetTheme}
  // },
  components: {
    NavigationComponent
  },
  created(){

    if(!localStorage.getItem('theme')) {
      localStorage.setItem('theme', 'dark')
    }

  },
  methods: {
    toggleDarkMode(){

      if(localStorage.getItem('theme') === 'dark') {
        document.documentElement.setAttribute('data-theme', 'light')
        localStorage.setItem('theme', 'light')
      } else {
        document.documentElement.setAttribute('data-theme', 'dark')
        localStorage.setItem('theme', 'dark')
      }

    }
  }
  
})
</script>

<style lang="scss">
@import './assets/sass/variables.scss';
@import './assets/sass/normalize.scss';
@import './assets/sass/globals.scss';
body{
  background-color: var(--background);
  color: var(--body-color);
}

.container{
  max-width:1140px;
  margin: 0 auto;
}
</style>
