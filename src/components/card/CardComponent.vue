<template>
  <div class="card">
    <div class="card__content">
      <p class="card__title">
        {{ title }}
      </p>
      <h2 class="card__body">
        {{ body }}
      </h2>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted  } from 'vue';

export default defineComponent({
  name: 'CardComponent',
  props: {
    title: {
      type: String,
      required: false
    },
    body: {
      type: String,
      required: false
    }

  },
	
});
</script>

<style scoped lang="scss">
  .card{
    display: flex;
    flex-wrap:wrap;
    justify-content: center;
    align-items: center;
    border-left: solid 2px var(--info);
    border-radius:5px;
    padding:1rem;
    background-color: var(--card-background-color);
    &__title{
      text-align: center;
      flex: 1 1 100%;
      margin:0;
      color: var(--gray-text);
    }
    &__body{
      text-align: center;
      flex: 1 1 100%;
      margin:0;
      color: var(--body-color);
    }
  }
</style>
