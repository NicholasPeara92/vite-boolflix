<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";

export default {
  components: {
    AppCard,
    // AppCardTv,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <section class="my-container py-4">
    <section class="movies py-5">
      <h2>Film</h2>
      <ul>
        <AppCard v-for="movie in store.movies" :info="movie" />
      </ul>
    </section>
    <section class="series">
      <h2>Serie TV</h2>
      <ul>
        <AppCard v-for="serie in store.series" :info="serie" />
      </ul>
    </section>
  </section>
</template>

<style lang="scss" scoped>
.my-container {
  background-color: rgb(29, 28, 28);
  min-height: 100vh;
}
ul {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  color: white;
  padding-left: 0;
}
h2 {
  color: white;
  margin-left: 62px;
}
</style>
