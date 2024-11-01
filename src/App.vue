<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'"/>
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <!-- v-model="currentTemp is to do 2 way binding. So changes in the template, like
             selecting a different radio button, will also update the variable holding the value.
             the v-model="currentTemp" will set the default value of this radioButton to the value of currentTemp." -->
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            <!-- the temp at this iteration will be the label for this radio button -->
            {{ temp }}
          </label>
        </template>
      </li>
    </ul>
    <ul>
      <li>
        <template v-for="base in bases" :key="base">
          <label>
            <!-- v-model="currentBase" is to do 2 way binding. So changes in the template, like
             selecting a different radio button, will also update the variable holding the value.
             the v-model="currentBase" will set the default value of this radioButton to the value of currentBase." -->
             <input
              type="radio"
              name="base"
              :id="`${base.id}`"
              :value="base"
              v-model="currentBase"
            />
            <!-- the base.name at this iteration will be the label for this radio button -->
            {{ base.name }}
          </label>
        </template>
      </li>
    </ul>
    <ul>
      <li>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
            <!-- v-model="currentCreamer" is to do 2 way binding. So changes in the template, like
             selecting a different radio button, will also update the variable holding the value.
             the v-model="currentCreamer" will set the default value of this radioButton to the value of currentCreamer." -->
             <input
              type="radio"
              name="creamer"
              :id="`r${creamer.id}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            <!-- the creamer.name at this iteration will be the label for this radio button -->
            {{ creamer.name }}
          </label>
        </template>
      </li>
    </ul>
    <ul>
      <li>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
            <!-- v-model="currentSyrup" is to do 2 way binding. So changes in the template, like
             selecting a different radio button, will also update the variable holding the value.
             the v-model="currentSyrup" will set the default value of this radioButton to the value of currentSyrup." -->
            <input
              type="radio"
              name="syrup"
              :id="`${syrup.id}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            <!-- the base.name at this iteration will be the label for this radio button -->
            {{ syrup.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp, currentCreamer, currentBase, currentSyrup, bases, creamers, syrups } from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
