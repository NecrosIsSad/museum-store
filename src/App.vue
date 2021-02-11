<template>
  <div id="app">
    <div class="content">
      <the-header />
      <the-store-items-container />
    </div>
    <the-footer />
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import TheFooter from "./components/TheFooter.vue";
import TheHeader from "./components/TheHeader.vue";
import TheStoreItemsContainer from "./components/TheStoreItemsContainer.vue";

export default {
  components: { TheHeader, TheStoreItemsContainer, TheFooter },
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

<style lang="scss">
#app {
  display: flex;
  flex-direction: column;
  height: 100%;
}

.content {
  flex: 1 0 auto;
}
</style>
