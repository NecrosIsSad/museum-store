<template>
  <div id="app">
    <Header />
    <the-store />
    <Footer />
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import TheStore from "./components/TheStore.vue";

export default {
  components: { Header, TheStore, Footer },
  name: "App",
  computed: {
    ...mapGetters(["PRODUCTS"])
  },
  methods: {
    ...mapActions(["GET_PRODUCTS_FROM_API"])
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API();
  }
};
</script>

<style lang="scss"></style>
