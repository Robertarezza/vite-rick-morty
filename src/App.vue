<script>
import axios from "axios";
import AppCards from "./components/AppCards.vue";
import AppHeader from "./components/AppHeader.vue";
import AppLoad from "./components/AppLoad.vue";

export default {
  components: {
    AppHeader,
    AppCards,
    AppLoad,
  },

  data() {
    return {
      cardsArray: [],
      isLoading: false,
    };
  },

  created() {
    this.isLoading = true;

    axios.get("https://rickandmortyapi.com/api/character").then((resp) => {
      console.log(resp);
      this.cardsArray = resp.data.results;
      console.log("Dati ricevuti:", resp.data.results);

      
        this.isLoading = false;
        console.log("fine caricamento");
      
      
    });
  },
};
</script>

<template>
  <AppHeader />
  <AppLoad v-if="isLoading" />
  <AppCards v-else :cardsArray="cardsArray" />
</template>

<style lang="scss"></style>
