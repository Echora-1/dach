<template>
  <section class="main-screen">
    <img
      class="main-screen__img"
      width="869"
      height="587"
      src="@/assets/images/main@2x.png"
      alt=""
    />
    <div class="main-screen__wrap container">
      <h1 class="base-title">{{ $t("Кровельные работы") }}</h1>
      <p class="main-screen__subtitle">{{ $t("Познань и область") }}</p>
      <base-button class="main-screen__btn">
        {{ $t("заказать") }}
      </base-button>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.base-title {
  max-width: 640px;
  margin-bottom: 12px;
  display: inline-block;
  padding: 25px 0 0 70px;
  position: relative;
  font-weight: 700;
  font-size: 87px;
  line-height: 106.26%;

  &::before {
    content: "";
    position: absolute;
    width: 864px;
    height: 178px;
    background: url("@/assets/images/main-title.svg") no-repeat center;
    left: 0;
    top: 0;
  }
}

.main-screen {
  min-height: 100vh;
  background-image: url("@/assets/images/main2.svg");
  background-position: 700px bottom;
  background-repeat: no-repeat;
  position: relative;

  &__wrap {
    width: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    text-align: end;
    padding-top: 176px;
    flex-direction: column;
    max-width: 1225px;
  }

  &__img {
    position: absolute;
    bottom: 0;
    left: 0;
    object-fit: contain;
  }

  &__subtitle {
    font-size: 37px;
    line-height: 56px;
    margin: 0 0 56px;
  }

  &__btn {
    min-height: 83px;
    max-width: 330px;
    width: 100%;
    font-weight: 500;
    font-size: 27px;
    line-height: 37px;
  }
}
</style>
<script setup>
import BaseButton from "@/components/base/BaseButton.vue";
</script>
