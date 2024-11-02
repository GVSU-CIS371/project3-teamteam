<template>
  <div class="syrup">
    <div v-for=" in 5" class="syrup" :style="applyStyle"></div>
  </div>
</template>


<script setup lang="ts">

import {currentSyrup} from '../stores/beverage';
import {computed} from 'vue';
const applyStyle = computed(() => {
    return {
        backgroundColor: currentSyrup.value.color
    };
})



</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
