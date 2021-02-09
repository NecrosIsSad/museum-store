<template>
  <button
    class="btn"
    :class="{
      btn_done: this.status == 'inCart',
      btn_fail: this.status == 'error'
    }"
    :disabled="this.status == 'error'"
    @click="clickToBuy()"
  >
    <svg
      v-if="this.status == 'inCart'"
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
    {{ innerStatus }}
    <div class="loader" v-if="this.status == 'loading'"></div>
  </button>
</template>

<script>

export default {
  data() {
    return {
    };
  },
  props: {
    status: {
      type: String,
      default() {
        return "";
      }
    },
    buttonCapture: {
      type: Object,
      default() {
        return {};
      }
    }
  },
  name: "Button",
  computed: {
    innerStatus() {
      return this.buttonCapture.[this.status];
    }
  },
  methods: {
    clickToBuy() {
      this.$emit('addToCart');
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
