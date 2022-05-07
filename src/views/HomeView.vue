<template>
  <div class="home">

    <div class="dashboard-hero">
      <div class="dashboard-hero__left">
        <div class="dashboard-hero__left__cards">
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'XCH Price'"
            :body="'$9999.99'"
          />
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'Pool Size'"
            :body="'35PiB'"
          />
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'Fee'"
            :body="'0%'"
          />
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'Farmers'"
            :body="'292'"
          />
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'Blocks'"
            :body="'567'"
          />
          <CardComponent
            class="dashboard-hero__left__cards_card"
            :title="'Pay Period'"
            :body="'24HR'"
          />
        </div>
        
      </div>
      <div class="dashboard-hero__right">
        <h1>Ready For Launch?</h1>
        <p>We are SpaceFarmers.io and we are a fantastic community that not only farms together, but we support each other as well!</p>
        <div class="dashboard-hero__right__actions">
          <button class="btn btn--info">
            Get Started
          </button>
          <p>or come chat on Discord and Telegram</p>
        </div>
      </div>
    </div>




    

    <pre>
      {{ data }}      
    </pre>
  </div>

    

    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
</template>

<script lang="ts">
import axios from 'axios'
import { defineComponent, ref } from 'vue';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import CardComponent from '@/components/card/CardComponent.vue'

export default defineComponent({
  name: 'HomeView',
  components: {
    // HelloWorld,
    CardComponent
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

<style lang="scss" scoped>
.dashboard-hero{
  margin-top:3rem;
  display:grid;
  gap: 1rem;
  grid-template-columns: 5fr 4fr;
  &__left{
    &__cards{
      display:grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap:1rem;
    }
  }
}
</style>