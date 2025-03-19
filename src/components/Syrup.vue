<template>
  <div 
    class="syrup" 
    :style="{ backgroundColor: currentSyrup === 'transparent' ? 'transparent' : currentSyrup }"
  ></div>
</template>

<script setup lang="ts">
import { currentSyrup } from "../stores/beverage";
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 40%;
  z-index: 150;
  animation: pour-tea 2s 1s forwards;
}
</style>