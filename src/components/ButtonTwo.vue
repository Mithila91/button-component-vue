<template>
  <button
    @mouseover="isHoveringTwo = true"
    @mouseleave="isHoveringTwo = false"
    :class="{ hovering: isHoveringTwo }"
    @click="onClick"
    class="btn"
    :style="{ background: colorTwo }"
  >
    {{ textTwo }}
  </button>
</template>

<script>
import { ref } from "vue";
export default {
  props: ["textTwo", "colorTwo", "isHoveringTwo"],
};
</script>

<style>
</style>