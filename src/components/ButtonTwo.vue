<template>
  <button
    @mouseover="isHoveringTwo = true"
    @mouseleave="isHoveringTwo = false"
    :class="{ hovering: isHoveringTwo }"
    @click="handleClick"
    class="btn"
    :style="{ background: colorTwo }"
  >
    {{ textTwo }}
  </button>
</template>

<script>
import { ref } from "vue";
export default {
  props: { textTwo: String, colorTwo: String, isHoveringTwo: Boolean },

  setup(props, context) {
    const handleClick = () => {
      context.emit("btnClickTwo");
    };
    return { handleClick };
  },
};
</script>

<style>
</style>