<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents v-if="hasSyrup">
      <template v-slot:top>
        <Creamer />
      </template>
      <template v-slot:mid>
        <Syrup />
      </template>
      <template v-slot:bottom>
        <Base />
      </template>
    </Contents>
    <Contents v-else>
      <template v-slot:top>
        <None />
      </template>
      <template v-slot:mid>
        <Creamer />
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
  hasSyrup: boolean;
};
defineProps<Props>();
</script>
