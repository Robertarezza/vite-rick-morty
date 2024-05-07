<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
      status: ["All", "unknown", "Alive", "Dead"],
    };
  },
};
</script>

<template>
  <div class="d-flex justify-content-center align-content-center flex-wrap-wrap">
    <h5>Seleziona i personaggi in base allo STATUS</h5>
    <select @change="$emit('filter')" v-model="store.selectedStatus">
      <option :value="statu" v-for="statu in status">
        {{ statu }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
select {
  width: 10%;
  margin: 0 auto;
}
</style>
