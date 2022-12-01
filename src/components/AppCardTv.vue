<script>
export default {
  props: {
    info: Object,
  },
  methods: {
    enFlag(string) {
      if (string === "en") {
        return "gb";
      } else if (string === "ko") {
        return "kr";
      } else return string;
    },
  },
  computed: {
    vote() {
      return Math.ceil(this.info.vote_average / 2);
    },
  },
};
</script>
<template>
  <li>
    <div class="my-card m-2">
      <img
        v-if="info.poster_path !== null"
        class="poster"
        :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`"
        :alt="info.name"
      />
      <img
        v-else
        src="https://via.placeholder.com/342x485"
        :alt="info.title"
        class="poster"
      />
      <div class="description">
        <h4>Titolo: {{ info.name }}</h4>
        <h6>Titolo originale: {{ info.original_name }}</h6>
        <span :class="`fi fi-${enFlag(info.original_language)}`"></span>
        <h6>Voto:</h6>
        <font-awesome-icon v-for="n in vote" icon="fa-solid fa-star" />
        <font-awesome-icon v-for="n in 5 - vote" icon="fa-regular fa-star" />
      </div>
    </div>
  </li>
</template>

<style lang="scss" scoped>
.my-card {
  width: 342px;
  position: relative;
}
.description {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 0;
  transition: 0.5s ease;
  background-color: black;
}
.my-card:hover .description {
  opacity: 1;
  cursor: pointer;
}
</style>
