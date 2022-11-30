<script>
export default {
  props: {
    title: String,
    originalTitle: String,
    originalLanguage: String,
    vote: Number,
  },
};
</script>
<template>
  <li>
    <div class="my-card">
      <img src="" alt="" />
      <h4>Titolo: {{ title }}</h4>
      <h6>Titolo originale: {{ originalTitle }}</h6>
      <h6>Lingua originale: {{ originalLanguage }}</h6>
      <h6>Voto: {{ vote }}</h6>
    </div>
  </li>
</template>

<style lang="scss" scoped>
.my-card {
  width: 342px;
}
</style>
