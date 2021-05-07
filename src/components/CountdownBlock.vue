<template>
  <div class="block-container">
    <div class="number">
      {{ value }}
    </div>
    <p class="label">{{ label }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';

export default defineComponent({
  name: 'Countdown',
  props: {
    value: {
      required: true,
      type: Number as PropType<number>,
    },
    label: {
      required: false,
      type: String as PropType<string>,
    },
  },
});
</script>

<style>
.block-container {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-direction: column;
}

.block-container .label {
  text-transform: uppercase;
  letter-spacing: 0.15rem;
  opacity: 0.8;
}

.block-container .number {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f90;
  padding: 1rem;
  border-radius: 8px;
  width: 125px;
  height: 100px;
  font-weight: 700;
  font-size: 2rem;
  box-shadow: 0px 10px 0px 0px hsl(210, 29%, 14%);
}
</style>
