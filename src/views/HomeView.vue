<template>
  <div class="main">
    <pre>
      {{ data }}      
    </pre>

    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
  </div>
</template>

<script lang="ts">
import axios from 'axios'
import { defineComponent, ref } from 'vue';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

export default defineComponent({
  name: 'HomeView',
  components: {
    // HelloWorld,
  },
  setup(){
    const API_BASE = process.env.VUE_APP_SPACE_FARMERS_API_PUBLIC_BASE
    const data = ref(Object)
    return { API_BASE, data }
  },
  // mounted() {
  //   this.getData()
  // },
  methods: {
    async getData(){
      this.data = await axios.get(this.API_BASE+'/farmers')
    }
  }
});
</script>
