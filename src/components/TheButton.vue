<template>
  <button class="btn" v-if="!this.$attrs.item.sold" @click.prevent="buy()">
    <svg
      v-if="this.button === 'В корзине'"
      width="16"
      height="13"
      viewBox="0 0 16 13"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M14.5316 1.80934L5.63353 11.2369L1.34826 7.19234"
        stroke="#F4F6F9"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
    {{ button }}
    <div class="loader" v-if="this.loader"></div>
  </button>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      button: "Купить",
      loader: false
    };
  },
  name: "Button",
  methods: {
    buy() {
      this.loader = true;
      this.button = "";

      setTimeout(() => {
        axios
          .get("https://jsonplaceholder.typicode.com/posts/1")
          .then(function() {
            console.log("good!");
          })
          .catch(function(error) {
            console.error(error);
          });
        this.loader = false;
        this.button = "В корзине";
      }, 3000); //имитация длительного запроса, для наглядной работы лоадера
    }
  }
};
</script>

<style scoped lang="scss">
.btn {
  background-color: #403432;
  width: 118px;
  height: 48px;
  border: none;
  color: #fff;
  outline: none;
  font-family: "Merriweather-Light";
  font-size: 14px;
  line-height: 21px;

  &:hover {
    background-color: #776763;
  }
}

.loader {
  border: 3px solid #fff;
  border-top: 3px solid #776763;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  animation: spin 2s linear infinite;
  margin: auto;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
