<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
import AppCardTv from "./AppCardTv.vue";

export default {
  components: {
    AppCard,
    AppCardTv,
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
    <section class="movies">
      <ul>
        <AppCard v-for="movie in store.movies" :info="movie" />
      </ul>
    </section>
    <section class="series">
      <ul>
        <AppCardTv v-for="serie in store.series" :info="serie" />
      </ul>
    </section>
  </section>
</template>

<style lang="scss" scoped>
.my-container {
  background-color: rgb(78, 75, 75);
  min-height: calc(100vh - 56px);
}
ul {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  color: white;
  padding-left: 0;
}
</style>
