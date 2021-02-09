<template>
  <ul class="nav">
    <li class="nav__item">
      <img
        class="nav__logo"
        :src="require(`../assets/images/${this.$attrs.logoSrc}`)"
        alt="logo"
      />
    </li>
    <li class="nav__item"><a href="/">Каталог</a></li>
    <li class="nav__item"><a href="/">Доставка</a></li>
    <li class="nav__item"><a href="/">Оплата</a></li>
    <li class="nav__item"><a href="/">Контакты</a></li>
    <li class="nav__item"><a href="/">О галерее</a></li>
  </ul>
</template>

<script>
export default {
  name: "Navigate"
};
</script>

<style scoped lang="scss">
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
