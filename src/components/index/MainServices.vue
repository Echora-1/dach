<template>
  <section class="services container">
    <div class="services__left">
      <div class="services__big-image">
        <h2 class="base-title base-title-mb">
          {{ $t("Наши") }} <span>{{ $t("услуги") }}</span>
        </h2>
        <img
          src="../../assets/images/services/s1@2x.png"
          width="389"
          height="669"
          alt=""
        />
        <div class="services__decor">
          <icon-decor-arrow />
        </div>
      </div>
      <div class="services__small-images">
        <img
          src="../../assets/images/services/s2@2x.png"
          width="267"
          height="338"
          alt=""
          class="services__small-image1"
        />
        <img
          src="../../assets/images/services/s3@2x.png"
          width="267"
          height="224"
          alt=""
          class="services__small-image2"
        />
        <div class="services__decor services__decor-mb">
          <icon-decor-arrow />
        </div>
      </div>
    </div>
    <div class="services__right">
      <h2 class="base-title">
        {{ $t("Наши") }} <span>{{ $t("услуги") }}</span>
      </h2>
      <ul class="services__list">
        <li
          class="services__item"
          v-for="(item, index) in $tm('список услуг')"
          :key="index"
        >
          {{ item }}
        </li>
      </ul>
      <base-button class="services__btn">
        {{ $t("Смотреть все") }}
      </base-button>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.base-title {
  padding-bottom: 20px;
  display: inline-block;
  position: relative;
  margin-top: 96px;
  margin-bottom: 45px;

  &::before {
    content: "";
    width: 90px;
    height: 1px;
    position: absolute;
    background: #b8b8b8;
    left: 0;
    bottom: 0;
  }

  @media (max-width: 1023px) {
    display: none;
  }
}

.base-title-mb {
  display: inline-block;
  padding: 0;
  margin: 13px 0 50px;

  &::before {
    display: none;
  }

  @media (min-width: 1024px) {
    display: none;
  }
}

.services {
  display: flex;
  width: 100%;

  @media (max-width: 1023px) {
    flex-direction: column;
  }

  &__left {
    display: flex;

    @media (max-width: 1023px) {
      max-width: 340px;
      margin: 0 auto;
    }
  }

  &__right {
    display: flex;
    flex-direction: column;

    @media (min-width: 1024px) {
      margin-left: 90px;
    }
  }
  &__big-image {
    z-index: 2;
    position: relative;

    img {
      max-height: 669px;
      max-width: 389px;
      width: 100%;
      height: 100%;
      object-fit: contain;
    }

    @media (max-width: 1023px) {
      display: flex;
      flex-direction: column;

      img {
        margin-top: 0;
        max-width: 195px;
        max-height: 335px;
      }
    }
  }

  &__small-image1 {
    @media (max-width: 1023px) {
      width: 134px;
      height: 238px;
    }
  }

  &__small-image2 {
    @media (max-width: 1023px) {
      width: 134px;
      height: 146px;
    }
  }

  &__small-images {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
    flex-grow: 1;
    position: relative;
    z-index: 1;
    margin-top: 190px;

    img {
      margin-bottom: 20px;
    }

    &::before {
      content: "";
      width: 176px;
      height: 173px;
      position: absolute;
      border: 1px solid #bbbbbb;
      left: -124px;
      top: 38px;
      z-index: -1;
    }

    @media (max-width: 1023px) {
      margin-left: 9px;
      margin-top: 0;

      img {
        margin-bottom: 9px;
      }

      &::before {
        left: -109px;
        top: 122px;
        border-bottom: none;
      }

      &::after {
        content: "";
        width: 176px;
        height: 173px;
        position: absolute;
        border-right: 1px solid #bbbbbb;
        border-bottom: 1px solid #bbbbbb;
        left: -98px;
        bottom: 14px;
        z-index: -1;
      }
    }
  }

  &__decor {
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--primary);
    width: 62px;
    height: 62px;
    margin-left: auto;
    transform: scaleX(-1);
    margin-top: 18px;

    @media (max-width: 1023px) {
      width: 51px;
      height: 51px;
      display: none;
      margin-left: unset;
      transform: scaleX(1);
      margin-top: 0;

      svg {
        width: 23px;
        height: 23px;
      }
    }
  }

  &__decor-mb {
    display: none;

    @media (max-width: 1023px) {
      display: flex;
    }
  }

  &__list {
    margin: 0 0 40px;

    @media (max-width: 1023px) {
      margin: 35px 0 20px;
    }
  }

  &__item {
    max-width: 415px;
    margin-bottom: 10px;
    font-size: 20px;
    line-height: 30px;
    padding-left: 25px;
    position: relative;

    &::before {
      content: "";
      width: 9px;
      height: 9px;
      background: var(--primary);
      position: absolute;
      left: 0;
      top: 10px;
    }

    @media (max-width: 1023px) {
      text-align: center;
      font-size: 14px;
      padding-left: 0;
      padding-bottom: 14px;
      margin: 0 auto 14px;
      line-height: 21px;
      max-width: 290px;

      &::before {
        width: 63px;
        height: 1px;
        bottom: 0;
        top: unset;
        left: 50%;
        transform: translateX(-50%);
      }
    }
  }

  &__btn {
    max-width: 278px;

    @media (max-width: 1023px) {
      margin: 0 auto;
      max-width: 172px;
    }
  }
}
</style>
<script setup>
import IconDecorArrow from "@/components/icon/IconDecorArrow.vue";
import BaseButton from "@/components/base/BaseButton.vue";
</script>
