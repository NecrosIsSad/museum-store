<template>
  <footer class="footer">
    <div class="footer__content">
      <ul class="nav">
        <li class="nav__item">
          <img
            class="nav__logo"
            src="../assets/images/logo-footer.png"
            alt="logo"
          />
        </li>
        <li class="nav__item"><a href="/">Каталог</a></li>
        <li class="nav__item"><a href="/">Доставка</a></li>
        <li class="nav__item"><a href="/">Оплата</a></li>
        <li class="nav__item"><a href="/">Контакты</a></li>
        <li class="nav__item"><a href="/">О галерее</a></li>
      </ul>
      <div class="footer__contact-wrap">
        <div class="footer__contacts">
          <img
            class="footer__phone-pic"
            src="../assets/images/phone.png"
            alt=""
          />
          <a class="footer__contact-info" href="tel:+74955555555"
            >+7 (495) 555-55-55</a
          >
        </div>
        <div class="footer__contacts">
          <img class="footer__map-pic" src="../assets/images/map.png" alt="" />
          <p class="footer__contact-info">г. Москва, ул. Расплетина, 24</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style scoped lang="scss">
.footer {
  height: 96px;
  background-color: #eceaea;
  margin: 320px 0 0 0;

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
  width: 615px;
  list-style: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0;
  font-family: "Merriweather-Regular";
  font-size: 14px;
  line-height: 21px;
  color: #343030;
  margin: 0;

  &__logo {
    height: 48px;
    width: 48px;
    position: relative;
    top: 3px;
  }

  a {
    text-decoration: none;
    font-family: "Merriweather-Regular";
    font-size: 14px;
    line-height: 21px;
    color: #343030;
    cursor: pointer;
  }
}
</style>
