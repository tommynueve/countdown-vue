<template>
  <h1 class="title">Countdown to my birthday</h1>
  <Countdown />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Countdown from './components/Countdown.vue';

export default defineComponent({
  name: 'App',
  components: {
    Countdown,
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.title {
  margin: 8rem 0;
  text-transform: uppercase;
  letter-spacing: 0.25rem;
  font-size: 1.5rem;
}
</style>
