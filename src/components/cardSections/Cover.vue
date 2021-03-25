<template>
  <img
    v-if="imageSrc"
    class="cover-image"
    :src="imageSrc"
    alt="View of a hotel room"
    :style="styleObj"
  />
</template>

<script>
export default {
  name: "Cover",
  props: {
    sectionData: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    styleObj() {
      return {
        height: this.sectionData.height ?? "auto",
        width: this.sectionData.width ?? "auto"
      };
    },
    imageSrc() {
      if (!this.sectionData.coverImage) {
        return;
      }
      const preparedFileName = this.sectionData.coverImage.toLowerCase();
      return require(`../../assets/${preparedFileName}`);
    }
  }
};
</script>
