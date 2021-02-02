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
        <li class="nav__item">Каталог</li>
        <li class="nav__item">Доставка</li>
        <li class="nav__item">Оплата</li>
        <li class="nav__item">Контакты</li>
        <li class="nav__item">О галерее</li>
      </ul>
      <div class="footer__contact-wrap">
        <div class="footer__contacts">
          <img
            class="footer__phone-pic"
            src="../assets/images/phone.png"
            alt=""
          />
          <p>+7 (495) 555-55-55</p>
        </div>
        <div class="footer__contacts">
          <img class="footer__map-pic" src="../assets/images/map.png" alt="" />
          <p>г. Москва, ул. Расплетина, 24</p>
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
  width: 100%;
  height: 96px;
  background-color: #eceaea;
  margin: 320px 0 0 0;

  &__content {
    margin: 0 auto 0 auto;
    width: 1216px;
    padding: 24px 0;
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

    p {
      margin: 0;
      font-family: "Merriweather-Regular";
      font-size: 14px;
      line-height: 21px;
      color: #343030;
    }
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
}
</style>
