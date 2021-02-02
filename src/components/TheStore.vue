<template>
  <div class="wrap">
    <h1 class="title">Картины эпохи Возрождения</h1>
    <section class="store">
      <div
        class="store__item"
        :class="{ store__item_opacity: item.sold }"
        v-for="item in products"
        :key="item.id"
      >
        <img :src="require(`../assets/images/${item.src}`)" />
        <div class="store__name">
          <p>{{ item.name }}</p>
          <p>{{ item.author }}</p>
        </div>
        <div class="store__price" :class="{ store__price_sold: item.sold }">
          <div class="store__price-wrap">
            <p class="store__sale" v-if="item.sale && !item.sold">
              {{ item.sale }}
            </p>
            <p class="store__full-price" v-if="!item.sold">{{ item.price }}</p>
            <p class="store__sold" v-if="item.sold">Продана на аукционе</p>
          </div>
          <!-- <button class="store__btn" v-if="!item.sold" @click.prevent="buy()">
            {{ button }}
            <div class="loader"></div>
          </button> -->
          <the-button v-if="!item.sold" :item="item" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";
export default {
  components: { TheButton },
  name: "TheStore",
  computed: {
    products() {
      return this.$store.getters.PRODUCTS;
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
.store {
  display: flex;
  justify-content: space-between;

  &__item {
    width: 280px;
    height: 328px;
    border: 1px solid #e1e1e1;

    &_opacity {
      opacity: 0.6;
    }
  }

  &__name {
    color: #343030;
    font-family: "Merriweather-Regular";
    font-size: 18px;
    line-height: 27px;
    margin: 20px 0 0 24px;

    p {
      margin: 0;
    }
  }

  &__price {
    margin: 22px 24px 24px 24px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    p {
      margin: 0;
    }

    &_sold {
      margin: 34px 0 0 24px;
    }
  }

  &__sale {
    color: #a0a0a0;
    font-size: 14px;
    line-height: 21px;
    text-decoration: line-through;
    font-family: "Merriweather-Light";
  }

  &__full-price {
    font-size: 16px;
    line-height: 24px;
    color: #343030;
    font-family: "Merriweather-Regular";
  }

  &__sold {
    font-size: 16px;
    line-height: 24px;
    font-family: "Merriweather-Regular";
  }
}
</style>
