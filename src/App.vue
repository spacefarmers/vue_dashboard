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

  setup(){
    const theme = ref('')
    const targetTheme = ref('')

    return {theme, targetTheme}
  },

  created(){

    if(!localStorage.getItem('theme')) {
      localStorage.setItem('theme', 'dark')
    }

    // this.theme = localStorage.getItem('theme') || (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : '');

    // if(this.theme) {
    //   document.documentElement.setAttribute('data-theme', this.theme)
    // }

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
  /* Your default theme */
  --background: white;
  --foreground: black;
}
[data-theme='light'] {
  --background: black;
  --foreground: white;
}
[data-theme='dark'] {
  --background: green;
  --foreground: white;
}
body{
  background: var(--background);
}
</style>
