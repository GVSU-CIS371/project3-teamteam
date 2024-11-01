<template>
  <div class="baseBeverage" :style="customStyle">
    
  </div>
</template>

<script setup lang="ts">
// '../stores/beverage' will act as 
import { currentBase } from '../stores/beverage';
import {computed} from 'vue';
const customStyle = computed(() => {
    return {
        backgroundColor: currentBase.value.color
    }
})
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
