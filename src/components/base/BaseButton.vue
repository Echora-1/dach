<template>
  <button
    :class="[
      'common-button',
      {
        'common-button--loading': loading,
      },
    ]"
    :disabled="disabled"
    @click="click"
  >
    <slot></slot>
    <span class="loader-wrap">
      <span v-if="loading" class="loader"></span>
    </span>
  </button>
</template>

<script>
export default {
  props: {
    loading: {
      type: Boolean,
      default: false,
    },
  },

  methods: {
    click() {
      this.$emit("click");
    },
  },
};
</script>

<style lang="scss" scoped>
.common-button {
  background: var(--primary);
  cursor: pointer;
  color: #ffffff;
  font-weight: 500;
  font-size: 22px;
  line-height: 30px;
  text-align: center;
  display: flex;
  align-items: center;
  padding: 18px 25px;
  justify-content: center;
  position: relative;
  text-transform: uppercase;
  min-width: 172px;
  border: none;

  @media (max-width: 1023px) {
    font-size: 14px;
    line-height: 19px;
    padding: 11px 20px;
  }

  &:hover {
    opacity: 0.8;
  }

  &--loading {
    color: transparent;
    pointer-events: none;
  }
}

.loader-wrap {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.loader {
  width: 4px;
  height: 25px;
  border-radius: 4px;
  display: block;
  margin: 20px auto;
  position: relative;
  background: currentColor;
  color: #fff;
  box-sizing: border-box;
  animation: animloader 0.45s 0.3s linear infinite alternate;
}

.loader::after,
.loader::before {
  content: "";
  width: 4px;
  height: 25px;
  border-radius: 4px;
  background: currentColor;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 11px;
  box-sizing: border-box;
  animation: animloader 0.45s 0.45s linear infinite alternate;
}
.loader::before {
  left: -11px;
  animation-delay: 0s;
}

@keyframes animloader {
  0% {
    height: 28px;
  }
  100% {
    height: 3px;
  }
}
</style>
