<template>
  <div id="app">
    <Header />
    <the-store-items-container />
    <Footer />
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue";
import TheStoreItemsContainer from "./components/TheStoreItemsContainer.vue";

export default {
  components: { Header, TheStoreItemsContainer, Footer },
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
