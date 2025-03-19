<template>
  <Mug>
    <!-- Conditionally render Hot or Cold -->
    <Cold v-if="isIced" />
    <Hot v-else />

    <!-- Contents with Conditional Rendering -->
    <Contents>
      <!-- Creamer (Top Slot) -->
      <template v-slot:top>
        <Creamer v-if="currentCreamer !== 'transparent'" />
      </template>

      <!-- Syrup (Mid Slot) -->
      <template v-slot:mid>
        <Syrup v-if="currentSyrup !== 'transparent'" />
      </template>

      <!-- Base Beverage (Bottom Slot) -->
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
import { currentCreamer, currentSyrup } from "../stores/beverage"; // Import reactive state

type Props = {
  isIced: boolean;
};
defineProps<Props>();
</script>