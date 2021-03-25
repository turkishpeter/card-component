<template>
  <div @click="getClickAction" class="card-container">
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
    },
    clickAction: {
      type: String,
      default: ""
    }
  },
  methods: {
    alertAction() {
      alert("This is an alert message.");
    },
    visitVuejs() {
      window.location.replace("https://vuejs.org");
    },
    getClickAction() {
      if (!this.clickAction) {
        return;
      }
      this[this.clickAction]();
    }
  }
};
</script>

<style>
.card-container {
  display: flex;
  min-width: 300px;
  flex-direction: column;
  border-radius: 0.25rem;
  border: 1px solid rgba(45, 45, 45, 0.2);
  width: min-content;
  cursor: pointer;
  user-select: none;
}
.card-container:hover {
  background: rgba(45, 45, 45, 0.04);
}
</style>
