<script>
import axios from "axios";
import { store } from "./store";
import AppCards from "./components/AppCards.vue";
import AppHeader from "./components/AppHeader.vue";
import AppLoad from "./components/AppLoad.vue";
import AppSearch from "./components/AppSearch.vue";


export default {
  components: {
    AppHeader,
    AppCards,
    AppLoad,
    AppSearch,
  },

  data() {
    return {
      cardsArray: [],
      isLoading: false,
      store,
    
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
  methods: {
    getCards() {
      this.isLoading = true;
      // Costuriamo i parametri per la chiamata axios
       const paramsObj = {
       
       };

      // Se c'è il filtro applicato, aggiungo anche chiave status all'oggetto di params
      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
         console.log("Get cards", this.store.selectedStatus)
      }

      axios
        .get("https://rickandmortyapi.com/api/character", {
          params: paramsObj,
        })
        .then((resp) => {
          this.cardsArray = resp.data.results;
          this.isLoading = false;
        });
    },
  },
};
</script>

<template>
  <AppHeader />
  <AppSearch  @filter="getCards"/>
  <AppLoad v-if="isLoading" />
  <AppCards v-else :cardsArray="cardsArray" />
</template>

<style lang="scss"></style>
