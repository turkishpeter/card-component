<template>
  <div class="card-container">
    <Loader v-if="isLoading" />
    <component
      v-for="(section, index) in cardData"
      :is="section.sectionName"
      :sectionData="section.data"
      :key="index"
    />
  </div>
</template>

<script>
import Loader from "@/components/loader/Loader.vue";
import Cover from "@/components/cardSections/Cover.vue";
import Info from "@/components/cardSections/Info.vue";
import Body from "@/components/cardSections/Body.vue";
import Footer from "@/components/cardSections/Footer.vue";
export default {
  name: "CardWrapper",
  components: {
    Loader,
    Cover,
    Info,
    Body,
    Footer
  },
  props: {
    cardData: {
      type: Array,
      default: () => []
    },
    isLoading: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style>
.card-container {
  display: flex;
  min-width: 300px;
  flex-direction: column;
  border-radius: 4px;
  border: 1px solid rgba(45, 45, 45, 0.2);
  width: min-content;
}
</style>
