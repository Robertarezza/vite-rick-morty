<script>
import CardsList from "./CardsList.vue";
import { store } from "../store";

export default {
  components: {
    CardsList,
  },
  data() {
    return {
      store,
    };
  },
 
};
</script>

<template>
  <div class="container mt-5">
    <div class="row row-cols-4">
      <div class="col mb-4" v-for="card in store.cardsArray"  >
        <CardsList :cardObj="card"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>

</style>
