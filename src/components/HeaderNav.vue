<script>
export default {
  name: "HeaderNav",
  data() {
    return {
      links: [
        "Home",
        "Serie TV",
        "Film",
        "Nuovi e popolari",
        "La mia lista",
        "Sfoglia per lingua",
      ],
    };
  },
};
</script>
<template>
  <nav class="main-nav">
    <ul>
      <li v-for="link in links">
        <a href="#">{{ link }}</a>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
.main-nav {
  ul {
    display: flex;
    list-style: none;
    justify-content: center;
    margin-bottom: 0;
    padding-left: 0;
    li {
      position: relative;
      a {
        display: inline-block;
        padding: 20px 10px;
        text-decoration: none;
        color: white;
        font-weight: bold;
      }
    }
  }
}
</style>
