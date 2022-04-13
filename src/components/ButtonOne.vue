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

<style>
.btn {
  display: block;
  margin: 20px auto 0;
  color: white;
  padding: 10px;
  border: 0;
  border-radius: 6px;
  font-size: 16px;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

.btn.hovering {
  transform: scale(1.5);
}
</style>