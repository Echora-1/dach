<template>
  <button :class="['menu-button', { 'menu-button--open': open }]">
    <span class="menu-button__line"></span>
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    open: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.menu-button {
  border: none;
  background: transparent;
  width: 40px;
  height: 35px;
  position: relative;
  cursor: pointer;
  color: currentColor;
  padding: 0;
  text-align: center;
  transition: all 0.3s;

  &__line {
    display: flex;
    width: 100%;
    height: 3px;
    background: currentColor;
    margin: auto 0;
  }

  &::before,
  &::after {
    height: 3px;
    border-radius: 6px;
    background: currentColor;
    position: absolute;
    width: 40px;
  }

  &::before,
  &::after {
    content: " ";
    left: 50%;
    right: 0;
    transform: translateX(-50%);
    transition: all 0.3s;
  }

  &::before {
    top: 0;
  }

  &::after {
    bottom: 0;
  }

  &--open {
    padding: 30px 0 0;

    .menu-button__line {
      display: none;
    }

    &::before,
    &::after {
      top: 15px;
      bottom: unset;
      background: #ffffff;
    }

    &::before {
      transform: translateX(-50%) rotate(45deg);
    }

    &::after {
      transform: translateX(-50%) rotate(-45deg);
    }
  }

  @media (max-width: 1023px) {
    width: 24px;
    height: 21px;

    &__line {
      height: 2px;
    }

    &::before,
    &::after {
      height: 2px;
      border-radius: 0;
      width: 24px;
    }
  }
}
</style>
