<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";

export default {
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <ul>
    <AppCard
      v-for="movie in store.movies"
      :title="movie.title"
      :originalTitle="movie.original_title"
      :originalLanguage="movie.original_language"
      :vote="movie.vote_average"
    />
  </ul>
</template>

<style lang="scss" scoped>
ul {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>
