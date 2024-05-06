<script>
import axios from "axios";
import AppCards from "./components/AppCards.vue";
import AppHeader from "./components/AppHeader.vue";


export default {
  components: {
    AppHeader,
    AppCards,
  },
  
  data() {
    return {
      cardsArray: [],
    };
  },
  created() {
    axios
      .get("https://rickandmortyapi.com/api/character")
      .then((resp) => {
        console.log(resp);
       this.cardsArray = resp.data.results;
       console.log(resp.data.results );
      });
  },
};
</script>

<template>
 <AppHeader />
 <AppCards  :cardsArray="cardsArray"  />
</template>

<style lang="scss">


</style>
