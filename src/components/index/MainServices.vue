<template>
  <section class="services container">
    <div class="services__left">
      <img
        src="../../assets/images/services/s1@2x.png"
        width="389"
        height="669"
        alt=""
        class="services__big-image"
      />
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
        <div class="services__decor">
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
}

.services {
  display: flex;
  width: 100%;

  &__left {
    display: flex;
  }

  &__right {
    margin-left: 90px;
    display: flex;
    flex-direction: column;
  }
  &__big-image {
    margin-top: 100px;
    max-height: 669px;
    max-width: 389px;
    width: 100%;
    height: 100%;
    z-index: 2;
    position: relative;
  }

  /*  &__small-image1 {
    max-height: 338px;
    max-width: 267px;
    width: 100%;
    height: 100%;
  }

  &__small-image2 {
    max-height: 224px;
    max-width: 267px;
    width: 100%;
    height: 100%;
  } */

  &__small-images {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
    flex-grow: 1;
    position: relative;
    z-index: 1;

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
  }

  &__decor {
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--primary);
    width: 62px;
    height: 62px;
  }

  &__list {
    margin: 0 0 40px;
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
  }

  &__btn {
    max-width: 278px;
  }
}
</style>
<script setup>
import IconDecorArrow from "@/components/icon/IconDecorArrow.vue";
import BaseButton from "@/components/base/BaseButton.vue";
</script>
