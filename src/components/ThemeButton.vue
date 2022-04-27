<template>
<button>
	dark
</button>
<button>
	light
</button>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted  } from 'vue';

export type UserTheme = 'light' | 'dark';

//TODO -- set up a toggle like in net ninja to toggle the dark mode
export default defineComponent({
  name: 'ThemeButton',
  props: {
    msg: String,
  },
	
});
</script>

<style scoped lang="scss">

</style>
