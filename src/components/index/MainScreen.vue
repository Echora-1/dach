<template>
  <section class="main-screen">
    <img
      class="main-screen__img"
      width="869"
      height="587"
      src="@/assets/images/main@2x.png"
      alt=""
    />
    <div class="decor"></div>
    <div class="decor1"></div>
    <div class="main-screen__wrap container">
      <h1 class="base-title">{{ $t("Кровельные работы") }}</h1>
      <p class="main-screen__subtitle">{{ $t("Познань и область") }}</p>
      <base-button class="main-screen__btn">
        {{ $t("заказать") }}
      </base-button>
      <main-arrow class="arrow" />
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

  @media (min-width: 1024px) {
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

  @media (max-width: 1023px) {
    font-size: 43px;
    line-height: 45px;
    text-align: center;
    padding: 0;
    max-width: 340px;
  }
}

.main-screen {
  min-height: 100vh;
  background-image: url("@/assets/images/main2.svg");
  background-position: 700px bottom;
  background-repeat: no-repeat;
  position: relative;

  @media (max-width: 1023px) {
    min-height: 600px;
    background-image: url("@/assets/images/mb-main2.svg");
    background-position: 0px bottom;
  }

  &__wrap {
    width: 100%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    text-align: end;
    padding-top: 176px;
    flex-direction: column;
    max-width: 1225px;
    position: relative;
    z-index: 2;

    @media (max-width: 1023px) {
      flex-direction: column;
      padding-top: 149px;
      align-items: center;
    }
  }

  &__img {
    position: absolute;
    bottom: 0;
    left: 0;
    object-fit: contain;
    z-index: 1;

    @media (max-width: 1023px) {
      max-width: 306px;
      max-height: 223px;
    }
  }

  &__subtitle {
    font-size: 37px;
    line-height: 56px;
    margin: 0 0 56px;

    @media (max-width: 1023px) {
      font-size: 17px;
      line-height: 33px;
      margin: 0 0 23px;
    }
  }

  &__btn {
    min-height: 83px;
    max-width: 330px;
    width: 100%;
    font-weight: 500;
    font-size: 27px;
    line-height: 37px;

    @media (max-width: 1023px) {
      font-size: 14px;
      line-height: 19px;
      padding: 11px 20px;
      min-height: unset;
      max-width: 172px;
    }
  }
}

.decor {
  width: 64px;
  height: 128px;
  border: 1px solid #e2e2e2;
  position: absolute;
  bottom: 172px;
  left: 0;
  z-index: 0;

  @media (min-width: 1024px) {
    display: none;
  }
}

.decor1 {
  width: 41px;
  height: 85px;
  border: 1px solid #e2e2e2;
  position: absolute;
  bottom: 279px;
  right: 0;
  z-index: 0;

  @media (min-width: 1024px) {
    display: none;
  }
}
.arrow {
  position: absolute;
  bottom: -140px;
  right: 20px;

  @media (max-width: 1023px) {
    width: 34px;
    height: 34px;
    bottom: -234px;
  }
}
</style>
<script setup>
import BaseButton from "@/components/base/BaseButton.vue";
import MainArrow from "@/components/icon/MainArrow.vue";
</script>
