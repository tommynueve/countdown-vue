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
  font-size: 0.9rem;
  font-weight: 600;
}

.block-container .number {
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(hsl(36deg 100% 38%) 50%, 50%, #f90 100%);
  padding: 1rem;
  border-radius: 8px;
  width: 125px;
  height: 110px;
  font-weight: 700;
  font-size: 3rem;
  box-shadow: 0px 8px 0px 0px hsl(210, 29%, 14%);
  position: relative;
  overflow: hidden;
}

.number::before {
  content: '';
  height: 10px;
  width: 10px;
  border-radius: 50%;
  position: absolute;
  background-color: hsl(210, 29%, 14%);
  top: 50%;
  transform: translateY(-5px);
  left: -5px;
}

.number::after {
  content: '';
  height: 10px;
  width: 10px;
  border-radius: 50%;
  position: absolute;
  background-color: hsl(210, 29%, 14%);
  top: 50%;
  transform: translateY(-5px);
  right: -5px;
}
</style>
