<script>
export default {
  props: {
    cardObj: Object,
  },
  data() {
    return {};
  },
  computed: {
    status () {
        if (this.cardObj.status === "unknown") {
         return  "NO STATUS ";
      } else {
        return this.cardObj.status;
      }
    },
  },
};
</script>

<template>
  <div class="card">
    <img :src="cardObj.image" alt="" />
    <div class="card-body">
      <h2>{{ cardObj.name }}</h2>
      <p>{{ status }}</p>
      <!-- non c'è cardObj perche sto cambiando qualcosa nel computed -->
      <p>{{ cardObj.species }}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  border: none;
  background-color: transparent;

  img {
    border-radius: 50%;
  }

  h2 {
    text-align: center;
    margin-bottom: 2rem;
    font-weight: 400;
    font-size: 1.5rem;
  }
  p {
    text-align: center;
    margin-top: -8px;
    margin-bottom: 0rem;
  }
}
</style>
