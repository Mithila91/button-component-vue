<template>
  <div class="backDrop">
    <div>
      <h1>{{ heading }}</h1>
      <p>{{ paragraph }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["heading", "paragraph", "theme"],
  data() {
    return {};
  },
};
</script>

<style>
</style>