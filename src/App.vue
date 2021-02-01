<template>
  <div id="app">
    <Header />
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import Header from "./components/Header.vue";

export default {
  components: { Header },
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
