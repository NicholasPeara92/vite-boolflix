<script>
import { store } from "../store.js";
import HeaderNav from "./HeaderNav.vue";
export default {
  components: {
    HeaderNav,
  },
  data() {
    return {
      store,
      el: "#demo",
      show: true,
    };
  },
};
</script>

<template>
  <header class="px-3">
    <div class="d-flex">
      <a href="#"
        ><img
          src="https://fontmeme.com/permalink/221202/9f3ee58c6a1836d4b96733502d1620ac.png"
          alt="netflix-font"
          border="0"
      /></a>
      <HeaderNav />
    </div>
    <div class="d-flex align-items-center">
      <form @submit.prevent="$emit('search')" id="demo">
        <transition name="fade">
          <input
            v-if="show"
            type="text"
            placeholder="Cerca un titolo"
            v-model="store.searchText"
            required
          />
        </transition>
      </form>
      <button type="" v-on:click="show = !show">
        <i class="fa-solid fa-magnifying-glass"></i>
      </button>
      <i class="fa-regular fa-bell"></i>
      <i class="fa-regular fa-user"></i>
    </div>
  </header>
</template>

<style lang="scss" scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgba(0, 0, 0, 0.8);
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 10;
}
input {
  background-color: inherit;
  color: white;
  border: 1px solid white;
  margin-right: 20px;
  border-radius: 5px;
  padding-left: 10px;
}
button {
  background-color: inherit;
  color: white;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity, 1s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.fa-bell,
.fa-user {
  color: white;
  padding-left: 15px;
}
i:hover {
  color: red;
}
</style>
