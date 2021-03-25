<template>
  <div id="app">
    <button @click="toggleLoadingState" class="loading">
      Test loading state
    </button>
    <div class="card-page">
      <CardWrapper
        :isLoading="isLoading"
        v-for="(card, index) in cards"
        :key="index"
        :cardData="card.data"
        :clickAction="card.clickAction"
      />
    </div>
  </div>
</template>

<script>
import CardWrapper from "./components/CardWrapper.vue";
import { cardsData } from "@/services/cardService.js";
export default {
  name: "CardPage",
  components: {
    CardWrapper
  },
  data() {
    return {
      cards: cardsData,
      isLoading: false
    };
  },
  methods: {
    toggleLoadingState() {
      this.isLoading = !this.isLoading;
    }
  }
};
</script>

<style>
.loading {
  border-radius: 4px;
  border: 1px solid rgba(45, 45, 45, 0.2);
  padding: 12px;
  background: white;
  margin-bottom: 2rem;
}
.loading:focus,
.loading:active,
.loading:visited {
  border: 1px solid rgba(45, 45, 45, 0.2);
  outline: none;
}
.loading:hover {
  box-shadow: 2px 2px 5px rgba(45, 45, 45, 0.2);
}
.card-page {
  display: flex;
}
.card-page .card-container:not(:last-child) {
  margin-right: 2rem;
}
@media screen and (max-width: 1048px) {
  .card-page {
    flex-direction: column;
    align-items: center;
  }
  .card-container {
    margin-bottom: 2rem;
  }
  #app {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .card-page .card-container:not(:last-child) {
    margin-right: 0;
  }
}
</style>
