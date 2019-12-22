<template>
  <div id="app">
    <Skills />
  </div>
</template>

<script>
import Skills from "@/components/Skills";

export default {
  name: "app",
  components: {
    Skills
  }
};
</script>

<style lang="scss">
@tailwind base;
@tailwind components;
@tailwind utilities;
</style>
