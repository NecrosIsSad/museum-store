<template>
  <button
    class="btn"
    :class="{
      btn_done: successfulRequest,
      btn_fail: failedRequest
    }"
    :disabled="failedRequest"
    v-if="!this.$attrs.item.sold"
    @click.prevent="buy()"
  >
    <svg
      v-if="successfulRequest"
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
      buttonSuccesful: "В корзине",
      buttonFail: "Ошибка!",
      loader: false,
      statusInner: {
        default: "Купить",
        loading: "",
        succes: "В корзине",
        fail: "Ошибка!"
      },
      statusBtn: ""
    };
  },
  name: "Button",
  computed: {
    failedRequest() {
      return this.button === this.buttonFail;
    },
    successfulRequest() {
      return this.button === this.buttonSuccesful;
    }
  },
  methods: {
    buy() {
      this.loader = true;
      this.button = "";

      setTimeout(() => {
        axios
          .get("https://jsonplaceholder.typicode.com/posts/1")
          .then(
            function(response) {
              console.log(response);
              this.loader = false;
              this.button = this.buttonSuccesful;
            }.bind(this)
          )
          .catch(
            function(error) {
              console.error(error);
              this.loader = false;
              this.button = this.buttonFail;
            }.bind(this)
          );
      }, 3000); //имитация длительного ответа, для наглядной работы лоадера
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

  &_done {
    background-color: #5b3a32;
  }

  &_fail {
    background-color: #c1b4b1;
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
