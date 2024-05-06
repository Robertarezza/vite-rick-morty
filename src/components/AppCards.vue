<script>
import CardsList from "./CardsList.vue";

export default {
  components: {
    CardsList,
  },
  props: {
    cardsArray: Array,
  },

  data() {
    return {};
  },
};
</script>

<template>
  <div class="container mt-5">
    <div class="row row-cols-4">
      <div class="col mb-4" v-for="card in cardsArray">
        <CardsList :cardObj="card"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>

</style>
