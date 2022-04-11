<template>
  <button @click="onClick" class="btn" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "ButtonOne",
  props: {
    text: String,
    color: String,
    size: Boolean,
  },
  methods: {
    onClick() {
      this.$emit("toggle");
      console.log("I have been clicked");
    },
  },
};
</script>

<style>
</style>