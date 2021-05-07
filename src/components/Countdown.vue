<template>
  <div class="countdown-container">
    <CountdownBlock :value="days" label="Days" />
    <CountdownBlock :value="hours" label="Hours" />
    <CountdownBlock :value="minutes" label="Minutes" />
    <CountdownBlock :value="seconds" label="Seconds" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CountdownBlock from './CountdownBlock.vue';
import { endDate } from '../config/constants';

export default defineComponent({
  name: 'Countdown',
  components: {
    CountdownBlock,
  },
  methods: {
    start() {
      this.intervalHandler = setInterval(() => {
        const remaining = endDate - new Date().getTime();
        this.days = Math.floor(remaining / (1000 * 60 * 60 * 24));
        this.hours = Math.floor((remaining % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        this.minutes = Math.floor((remaining % (1000 * 60 * 60)) / (1000 * 60));
        this.seconds = Math.floor((remaining % (1000 * 60)) / 1000);
      }, 1000);
    },
  },
  data() {
    return {
      days: 0,
      minutes: 0,
      hours: 0,
      seconds: 0,
      intervalHandler: 0,
    };
  },
  mounted() {
    this.start();
  },
});
</script>

<style>
.countdown-container {
  display: flex;
  justify-content: center;
  gap: 2rem;
}
</style>
