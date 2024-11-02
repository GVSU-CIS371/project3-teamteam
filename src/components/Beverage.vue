<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <!-- if the hasCreamer variable is true, then we have a creamer option selected for this beverage, so we should render it.
         Otherwise, if no creamer is selected then we can ignore it and have the base fill up the mug up to the point of the creamer. -->
        <Creamer v-if="hasCreamer"/>
      </template>
      <template v-slot:mid>
        <!-- if the hasSyrup variable is true, then we have a syrup option selected for this beverage, so we should render it.
         Otherwise, if no syrup is selected then we can ignore it and have the base fill up the mug up to the point of the syrup. -->
         <Syrup v-if="hasSyrup" />
      </template>
      <template v-slot:bottom>
        <Base />
      </template>
    </Contents>

  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
//   added expected prop hasSyrup to be used by this component (beverage) in order to determine if syrup sub-component for this component (beverage) should be
// rendered or not 
hasSyrup: boolean;
//   added expected prop hasCreamer to be used by this component (beverage) in order to determine if creamer sub-component for this component (beverage) should be
// rendered or not 
  hasCreamer: boolean
};
defineProps<Props>();
</script>
