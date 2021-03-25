<template>
  <div class="container">
    <p class="text">{{ sectionData.footerText }}</p>
  </div>
</template>

<script>
export default {
  name: "CardFooter",
  props: {
    sectionData: {
      type: Object,
      default: () => {}
    }
  }
};
</script>

<style scoped>
.container {
  padding: 1.5rem;
  border-top: 1px solid rgba(45, 45, 45, 0.2);
}
.text {
  margin: 0;
  color: #6e6e6e;
  font-weight: 500;
}
</style>
