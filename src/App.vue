<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      store,
    };
  },
  created() {
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cards = resp.data.data;
      console.log(resp.data.data);
      console.log(this.store.cards);
    });
  },
  components: { AppHeader, AppMain },
};
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./style/general.scss";
</style>
