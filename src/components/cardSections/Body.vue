<template>
  <div class="container">
    <p class="text">{{ sectionData.bodyText }}</p>
  </div>
</template>

<script>
export default {
  name: "CardBody",
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
  max-width: 100%;
  padding: 0 1.5rem;
  margin-bottom: auto;
}
.text {
  width: 100%;
  margin: 0;
  margin-bottom: 1.5rem;
  font-size: 1rem;
  color: #2d2d2d;
}
</style>
