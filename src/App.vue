<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    searchMovie(data = "") {
      if (data === "reset") {
        this.store.searchText = "";
      }
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "25f24fd3ebdb2b8fa4786f77d8241b8d",
            query: this.store.searchText,
            language: "it-IT",
          },
        })
        .then((resp) => {
          this.store.movies = resp.data.results;
        })
        .catch((err) => {
          this.store.movies = [];
        });
    },
  },
};
</script>

<template>
  <div>
    <AppHeader @search="searchMovie" />
    <AppMain />
  </div>
</template>

<style lang="scss">
@import "./style/global.scss";
</style>
