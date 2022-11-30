<script>
export default {
  props: {
    info: Object,
  },
};
</script>
<template>
  <li>
    <div class="my-card m-2">
      <img
        class="poster"
        :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`"
        :alt="info.name"
      />
      <div class="description">
        <h4>Titolo: {{ info.name }}</h4>
        <h6>Titolo originale: {{ info.original_name }}</h6>
        <h6>Lingua originale: {{ info.original_language }}</h6>
        <h6>Voto: {{ info.vote_average }}</h6>
      </div>
    </div>
  </li>
</template>

<style lang="scss" scoped>
.my-card {
  width: 342px;
  height: 700px;
  border: 1px solid white;
}
</style>
