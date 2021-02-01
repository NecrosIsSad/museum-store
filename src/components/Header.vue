<template>
  <header class="header">
    <ul class="nav">
      <li class="nav__item">
        <img class="nav__logo" src="../assets/images/logo.png" alt="logo" />
      </li>
      <li class="nav__item">Каталог</li>
      <li class="nav__item">Доставка</li>
      <li class="nav__item">Оплата</li>
      <li class="nav__item">Контакты</li>
      <li class="nav__item">О галерее</li>
    </ul>
    <div class="search">
      <input
        type="text"
        class="search__input"
        placeholder="Поиск по названию картины"
      />
      <button class="search__btn">Найти</button>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
  margin: 0 auto;
  width: 1216px;
  display: flex;
  justify-content: space-between;
  height: 96px;
  align-items: center;
  border-bottom: 1px solid #e1e1e1;
}

.nav {
  width: 615px;
  list-style: none;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0;

  &__logo {
    height: 48px;
    width: 48px;
  }
}

.search {
  &__btn {
    background-color: #403432;
    width: 122px;
    height: 48px;
    border: none;
  }
}
</style>
