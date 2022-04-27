<template>
  <!-- <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav> -->


  <div class="main">
    
    <button @click="toggleDarkMode">
      toggle
    </button>
    <router-view/>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({

  // setup(){
  //   const theme = ref('')
  //   const targetTheme = ref('')

  //   return {theme, targetTheme}
  // },

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
:root {
  // default theme
  --background: #1A1D21;
  --body-color: white;
  --gray: #A8A8A8;
  --gray-text: #A8A8A8;
  --light-gray: #CED4D4;
  --light-gray-text: #CED4D4;
  --success: #13C54B;
  --warning: #E8BC52;
  --info: #2886F6;
  --card-background-color: #212529;
  --white: white;
}
[data-theme='light'] {
  --background: white;
  --body-color: #212529;
  --gray: #A8A8A8;
  --gray-text: #A8A8A8;
  --light-gray: #CED4D4;
  --light-gray-text: #CED4D4;
  --success: #13C54B;
  --warning: #E8BC52;
  --info: #2886F6;
  --card-background-color: #212529;
  --white: white;
}
[data-theme='dark'] {
  --background: #1A1D21;
  --body-color: white;
  --gray: #212529;
  --gray-text: #212529;
  --light-gray: #FCFCFC;
  --light-gray-text: #808D9B;
  --success: #13C54B;
  --warning: #E8BC52;
  --info: #2886F6;
  --card-background-color: #FCFCFC;
  --white: white;
}
body{
  background-color: var(--background);
  color: var(--body-color);
}
</style>
