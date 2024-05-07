<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
      
    };
  },
};
</script>

<template>
  <div>
    <h5>Visualizzati {{ store.cardsArray.length }} personaggi</h5> 
  </div>
</template>

<style lang="scss" scoped>
div {
  text-align: center;
 
}

</style>