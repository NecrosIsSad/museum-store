<template>
  <div class="wrap">
    <h1 class="title">Картины эпохи Возрождения</h1>
    <section class="store-grid">
      <the-store-item
        v-for="item in products"
        :key="item.id"
        :item="item"
        :isInCart="cartItems.includes(item.id)"
        @addToCart="addToCart"
      />
    </section>
  </div>
</template>

<script>
import TheStoreItem from "./TheStoreItem.vue";
export default {
  data() {
    return {
      cartItems: []
    };
  },
  components: { TheStoreItem },
  name: "TheStore",
  computed: {
    products() {
      return this.$store.getters.PRODUCTS;
    }
  },
  methods: {
    addToCart(itemId) {
      this.cartItems.push(itemId);
      localStorage.cartItems = this.cartItems;
    }
  },
  mounted() {
    if (localStorage.cartItems) {
      let newCartItems = Array.from(localStorage.cartItems);
      this.cartItems = newCartItems.filter(i => i != ",");
    }
  }
};
</script>

<style lang="scss">
.wrap {
  margin: 45px auto 0 auto;
  width: 1216px;
}

.title {
  margin: 0 0 40px 0;
  font-family: "Merriweather-Regular";
  font-size: 24px;
  line-height: 36px;
  color: #343030;
}
.store-grid {
  display: flex;
  justify-content: space-between;
}
</style>
