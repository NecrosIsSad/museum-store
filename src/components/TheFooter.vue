<template>
  <footer class="footer">
    <div class="footer__content">
      <the-navigate :logoSrc="logoSrc" />
      <div class="footer__contact-wrap">
        <div class="footer__contacts">
          <img
            class="footer__phone-pic"
            src="../assets/images/phone.svg"
            alt="phone"
          />
          <a class="footer__contact-info" href="tel:+74955555555"
            >+7 (495) 555-55-55</a
          >
        </div>
        <div class="footer__contacts">
          <img
            class="footer__map-pic"
            src="../assets/images/map.svg"
            alt="map marker"
          />
          <p class="footer__contact-info">г. Москва, ул. Расплетина, 24</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import TheNavigate from "./TheNavigate.vue";
export default {
  data() {
    return {
      logoSrc: "logo-footer.svg"
    };
  },

  components: { TheNavigate },
  name: "TheFooter"
};
</script>

<style scoped lang="scss">
.footer {
  height: 96px;
  background-color: #eceaea;
  margin: 290px 0 0 0;
  flex: 0 0 auto;
  &__content {
    margin: 0 auto 0 auto;
    width: 1216px;
    padding: 22px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__contact-wrap {
    width: 449px;
    display: flex;
    justify-content: space-between;
  }

  &__contacts {
    display: flex;
    align-content: center;
  }

  &__contact-info {
    margin: 0;
    font-family: "Merriweather-Regular";
    font-size: 14px;
    line-height: 21px;
    color: #343030;
    text-decoration: none;
  }

  &__phone-pic {
    width: 14px;
    height: 14px;
    margin-right: 10px;
    position: relative;
    top: 3px;
  }

  &__map-pic {
    width: 10px;
    height: 14px;
    margin-right: 10px;
    position: relative;
    top: 3px;
  }
}

.nav {
  margin: 0;
}
</style>
