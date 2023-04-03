<template>
  <div class="list">
    <a href="#main">{{ $t("Главная") }}</a>
    <a href="#services">{{ $t("Услуги") }}</a>
    <a href="#about">{{ $t("Наши преимущества") }}</a>
    <a href="#work">{{ $t("Как мы работаем") }}</a>
    <a href="#portfolio">{{ $t("Наше портфолио") }}</a>
    <a href="#contact">{{ $t("Контакты") }}</a>
    <a href="#footer">{{ $t("Обсудим ваш проект?") }}</a>
  </div>
</template>

<style lang="scss" scoped>
.list {
  a {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 14px;
    line-height: 130%;
    color: #ffffff;
    min-height: 39px;
    background: rgba(35, 35, 35, 0.97);
    cursor: pointer;
    position: relative;

    &::before {
      content: "";
      width: 100%;
      height: 1px;
      background: #c0c0c0;
      bottom: 0;
      left: 0;
      right: 0;
      position: absolute;
    }

    &:hover {
      color: #1fb537;
    }
  }

  @media (max-width: 1023px) {
    a {
      background: transparent;
      font-size: 15px;
      line-height: 130%;
      min-height: 53px;

      &:last-child {
        &::before {
          display: none;
        }
      }
    }
  }
}
</style>
