<template>
  <div class="item" :class="{ item_opacity: item.sold }">
    <img :src="require(`../assets/images/${item.src}`)" />
    <div class="item__name">
      <p>{{ item.name }}</p>
      <p>{{ item.author }}</p>
    </div>
    <div class="item__price" :class="{ item__price_sold: item.sold }">
      <div class="item__price-wrap">
        <p class="item__sale" v-if="item.sale && !item.sold">
          {{ item.sale }}
        </p>
        <p class="item__full-price" v-if="!item.sold">
          {{ item.price }}
        </p>
        <p class="item__sold" v-if="item.sold">
          Продана на аукционе
        </p>
      </div>
      <the-button
        v-if="!item.sold"
        :item="item"
        :buttonCapture="buttonCapture"
      />
    </div>
  </div>
</template>

<script>
import TheButton from "./TheButton.vue";
export default {
  data() {
    return {
      buttonCapture: {
        default: "Купить",
        inCart: "В корзине",
        loading: "",
        error: "Ошибка!"
      }
    };
  },
  props: {
    item: {
      type: Object,
      default() {
        return {};
      }
    }
  },
  components: { TheButton },
  name: "TheStoreItem",
  computed: {},
  methods: {}
};
</script>

<style lang="scss">
.item {
  width: 280px;
  height: 328px;
  border: 1px solid #e1e1e1;

  &_opacity {
    opacity: 0.6;
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
