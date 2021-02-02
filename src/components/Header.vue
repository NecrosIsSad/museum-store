<template>
  <header class="header">
    <ul class="nav">
      <li class="nav__item">
        <img class="nav__logo" src="../assets/images/logo.png" alt="logo" />
      </li>
      <li class="nav__item"><a href="/">Каталог</a></li>
      <li class="nav__item"><a href="/">Доставка</a></li>
      <li class="nav__item"><a href="/">Оплата</a></li>
      <li class="nav__item"><a href="/">Контакты</a></li>
      <li class="nav__item"><a href="/">О галерее</a></li>
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

<style scoped lang="scss">
.header {
  margin: 0 auto;
  width: 1216px;
  display: flex;
  justify-content: space-between;
  height: 96px;
  align-items: center;

  &:after {
    content: "";
    position: absolute;
    border-bottom: 1px solid #e1e1e1;
    top: 96px;
    width: 100%;
    left: 0;
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

.search {
  font-family: "Merriweather-Light";
  font-size: 14px;
  line-height: 21px;

  &__input {
    width: 294px;
    height: 48px;
    border: 1px solid #e1e1e1;
    border-right: none;
    padding: 0 0 0 16px;
    font-family: "Merriweather-Light";
    color: #343030;
    font-size: 14px;
    line-height: 21px;
    outline: none;
    background-color: #f6f3f3;

    &::placeholder {
      color: #9f9f9f;
    }

    &:focus {
      border: 1px solid #b5b5b5;
      height: 46px;
    }
  }

  &__btn {
    background-color: #403432;
    width: 122px;
    height: 48px;
    border: none;
    color: #fff;
    outline: none;

    &:hover {
      background-color: #776763;
    }
  }
}
</style>
