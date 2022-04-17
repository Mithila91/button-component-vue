<template>
  <button
    @mouseover="isHovering = true"
    @mouseleave="isHovering = false"
    :class="{ hovering: isHovering }"
    @click="onClick"
    class="btn"
    :style="{ background: color }"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "ButtonOne",
  props: {
    text: String,
    color: String,
    isHovering: Boolean,
  },

  methods: {
    onClick() {
      this.$emit("btnClick");
    },
  },
};
</script>

