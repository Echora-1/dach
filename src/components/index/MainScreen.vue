<template>
  <section class="main-screen">
    <div class="decor"></div>
    <div class="decor1"></div>
    <div class="main-screen__wrap container">
      <h1 class="base-title">{{ $t("Кровельные работы") }}</h1>
      <p class="main-screen__subtitle">{{ $t("Познань и область") }}</p>
      <base-button class="main-screen__btn">
        {{ $t("заказать") }}
      </base-button>
    </div>
    <picture>
      <source
        media="(min-width: 1024px)"
        srcset="@/assets/images/main.png 1x, @/assets/images/main@2x.png 2x"
      />
      <img
        class="main-screen__img"
        width="866"
        height="450"
        src="@/assets/images/mb-main.png"
        srcset="@/assets/images/mb-main@2x.png 2x"
        alt=""
      />
    </picture>
  </section>
</template>

<!--<picture>
<source type="image/webp" media="(min-width: 768px)" srcset="../../assets/images/main-screen.webp 1x, ../../assets/images/main-screen@2x.webp 2x">
<source type="image/webp" srcset="../../assets/images/main-screen-mb.webp 1x, ../../assets/images/main-screen-mb@2x.webp 2x">
<source media="(min-width: 768px)" srcset="../../assets/images/main-screen.png 1x, ../../assets/images/main-screen@2x.png 2x">
<img
        src="../../assets/images/main-screen-mb.png"
        width="232"
        height="354"
        alt=""
        srcset="../../assets/images/main-screen-mb@2x.png 2x"
        class="main-screen__img"
/>
</picture>-->

<style lang="scss" scoped>
.base-title {
  max-width: 640px;
  margin-bottom: 12px;
  display: inline-block;
  padding: 25px 70px 0 0;
  position: relative;
  font-weight: 700;
  font-size: 87px;
  line-height: 106.26%;
  text-align: start;

  @media (min-width: 1024px) {
    &::before {
      content: "";
      position: absolute;
      width: 864px;
      height: 178px;
      background: url("@/assets/images/main-title.svg") no-repeat center;
      right: 0;
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
  padding-top: 110px;
  min-height: 940px;
  position: relative;
  background-color: #f3f3f3;

  &::before {
    position: absolute;
    content: "";
    bottom: -110px;
    left: 0;
    right: 0;
    height: 282px;
    width: 100%;
    background-image: url("../../assets/images/bgMain.svg");
    background-repeat: no-repeat;
    background-size: cover;
    z-index: 2;
  }
  @media (min-width: 1024px) {
    &::after {
      position: absolute;
      content: "";
      bottom: 146px;
      left: 0;
      height: 118px;
      width: 1102px;
      background-image: url("../../assets/images/main-word.svg");
      background-repeat: no-repeat;
      z-index: 0;
    }
  }

  @media (max-width: 1023px) {
    min-height: 800px;
    overflow: hidden;
    padding-top: 50px;

    &::before {
      height: 218px;
      transform: scaleX(-1);
      bottom: -130px;
    }
  }

  &__wrap {
    width: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    text-align: end;
    padding-top: 90px;
    flex-direction: column;
    max-width: 1225px;
    position: relative;
    z-index: 2;

    @media (max-width: 1023px) {
      flex-direction: column;
      padding-top: 68px;
      align-items: center;
    }
  }

  &__img {
    position: absolute;
    top: 220px;
    right: 0;
    object-fit: contain;
    z-index: 1;
    width: 982px;
    height: 821px;

    @media (max-width: 1023px) {
      left: 50%;
      transform: translateX(-50%);
      bottom: 0;
      top: 160px;
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
  border: 1px solid #ffffff;
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
  border: 1px solid #ffffff;
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
</script>
