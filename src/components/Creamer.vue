<template>
    <!-- we add :style="customStyle" to say we want the :style to be updated, and customStyle is our function
     that calls the computed() funciton from vue. computed must return an object. which in our case:
     this object is unpacked to see that the backgroundColor is being set to what the currentBase's color is. -->
  <div class="froth">
    <div v-for=" in 5" class="foam" :style="applyStyle"></div>
  </div>
</template>

<script setup lang="ts">
import {currentCreamer} from '../stores/beverage';
import {computed} from 'vue';
const applyStyle = computed(() => {
    return {
        backgroundColor: currentCreamer.value.color
    };
})

</script>
<style lang="scss" scoped>
.froth {
  overflow: visible;
  transform: translateY(400%);
  position: relative;
  height: 20%;
  width: 100%;
  background-color: #c6c6c6;
  animation: pour-tea 2s 2s forwards;
}
.foam {
  display: block;
  background: #e4e0d2;
  border-radius: 30px;
  height: 40px;
  width: 40px;
  position: absolute;
}

.foam:nth-child(1) {
  top: 0px;
  left: -3px;
}

.foam:nth-child(2) {
  top: 0px;
  left: 55px;
}

.foam:nth-child(3) {
  width: 30px;
  height: 30px;
  border-radius: 40px;
  top: 3px;
  left: 30px;
}

.foam:nth-child(4) {
  width: 30px;
  height: 30px;
  border-radius: 45px;
  top: 5px;
  right: -2px;
}

.foam:nth-child(5) {
  top: 2px;
  right: 10px;
}
</style>
