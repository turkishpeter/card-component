<template>
  <div class="container">
    <img
      v-if="sectionData.thumbnailSrc"
      class="thumbnail"
      :src="imageSrc"
      :alt="sectionData.altText"
    />
    <div class="text-content">
      <h1 class="title" v-if="sectionData.title">{{ sectionData.title }}</h1>
      <h2 class="subtitle" v-if="sectionData.subtitle">
        {{ sectionData.subtitle }}
      </h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardInfo",
  props: {
    sectionData: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    imageSrc() {
      if (!this.sectionData.thumbnailSrc) {
        return;
      }
      const preparedFileName = this.sectionData.thumbnailSrc.toLowerCase();
      return require(`../../assets/${preparedFileName}`);
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  padding: 1.5rem;
}
.thumbnail {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  margin-right: 1.5rem;
}
.text-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.title {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0;
  color: #2d2d2d;
}
.subtitle {
  font-size: 0.875rem;
  font-weight: 500;
  margin: 0;
  color: #6e6e6e;
}
</style>
