<script>
import { store } from "../store";
import AppCard from "./components/AppCard.vue";

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
  <AppCard />
</template>

<style lang="scss" scoped></style>
