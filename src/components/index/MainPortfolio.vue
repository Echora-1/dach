<template>
  <div class="portfolio container">
    <div class="portfolio__left">
      <h2 class="base-title">
        {{ $t("Наше") }} <br />
        <span>{{ $t("портфолио") }}</span>
      </h2>
      <p>
        {{ $t("Мы гордимся") }}
      </p>
      <base-button class="portfolio__btn">
        {{ $t("Хочу так же!") }}
      </base-button>
    </div>
    <div class="portfolio__right">
      <div class="portfolio__info">
        <span>Название кейса{{ info }}</span>
      </div>
      <swiper
        :modules="modules"
        :slides-per-view="1"
        :space-between="0"
        :centeredSlides="true"
        :navigation="{
          prevEl: prev,
          nextEl: next,
        }"
        :pagination="true"
        @slideChange="onSlideChange"
      >
        <swiper-slide>
          <img
            src="../../assets/images/sl1.png"
            width="595"
            height="461"
            alt=""
          />
        </swiper-slide>
        <swiper-slide>
          <img
            src="../../assets/images/sl1.png"
            width="595"
            height="461"
            alt=""
          />
        </swiper-slide>
        <swiper-slide>
          <img
            src="../../assets/images/sl1.png"
            width="595"
            height="461"
            alt=""
          />
        </swiper-slide>
      </swiper>
      <button ref="prev" class="swiper-button-prev"></button>
      <button ref="next" class="swiper-button-next"></button>
      <base-button class="mb-btn"> {{ $t("Хочу так же!") }}</base-button>
    </div>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css/navigation";
import "swiper/css";
import "swiper/css/pagination";
import { Navigation, Pagination } from "swiper/core";
import BaseButton from "@/components/base/BaseButton.vue";
import { ref } from "vue";
export default {
  components: { BaseButton, Swiper, SwiperSlide },

  setup() {
    const prev = ref(null);
    const next = ref(null);
    const info = ref(1);
    const onSlideChange = (value) => {
      info.value = value.activeIndex + 1;
      console.log("slide change", value.activeIndex);
    };

    return {
      modules: [Navigation, Pagination],
      onSlideChange,
      prev,
      next,
      info,
    };
  },
};
</script>

<style lang="scss" scoped>
.base-title {
  position: relative;

  &::before {
    content: "";
    position: absolute;
    width: 113px;
    height: 1px;
    background: #b8b8b8;
    top: 52px;
    right: 20px;
  }

  @media (max-width: 1023px) {
    text-align: center;

    &:before {
      display: none;
    }
  }
}

.portfolio {
  padding-bottom: 177px;
  display: flex;
  justify-content: space-between;

  @media (max-width: 1023px) {
    flex-direction: column;
    justify-content: center;
    padding-left: 0;
    padding-right: 0;
    padding-bottom: 54px;
  }

  &__left {
    max-width: 400px;
    width: 100%;

    @media (max-width: 1023px) {
      max-width: 100%;
    }

    p {
      max-width: 362px;
      font-size: 20px;
      line-height: 30px;
      margin: 27px 0 65px;

      @media (max-width: 1023px) {
        margin: 17px auto 63px;
        font-size: 14px;
        line-height: 18px;
        text-align: center;
        max-width: 314px;
      }
    }
  }
  &__right {
    margin-left: 40px;
    margin-right: 40px;
    max-width: 594px;
    position: relative;

    @media (max-width: 1023px) {
      max-width: 100%;

      img {
        max-width: 340px;
        width: 100%;
        height: 100%;
      }
    }

    &::before {
      content: "";
      position: absolute;
      width: 176px;
      height: 173px;
      border: 1px solid #bbbbbb;
      right: -39px;
      bottom: -77px;

      @media (max-width: 1023px) {
        right: unset;
        left: -145px;
        bottom: 0px;
        height: 123px;
      }
    }

    &:deep {
      .swiper-pagination-bullet {
        border-radius: 0;
        background: white;
        opacity: 1;
      }
      .swiper-pagination-bullet-active {
        background: var(--primary);
      }

      .swiper-pagination-horizontal {
        bottom: 20px;
      }

      .swiper-button-prev {
        background: url("@/assets/images/swiperBtn.svg") no-repeat center;
        border: none;
        left: -40px;
        &::after {
          display: none;
        }

        @media (max-width: 1023px) {
          left: -30px;
          transform: translateY(-70%);
        }
      }

      .swiper-button-next {
        background: url("@/assets/images/swiperBtn.svg") no-repeat center;
        transform: scale(-1);
        border: none;
        right: -40px;

        &::after {
          display: none;
        }

        @media (max-width: 1023px) {
          right: -30px;
          transform: scale(-1) translateY(70%);
        }
      }
    }
  }

  &__btn {
    max-width: 278px;
    width: 100%;

    @media (max-width: 1023px) {
      display: none;
    }
  }

  &__info {
    position: absolute;
    left: -77px;
    top: -30px;
    z-index: 2;
    max-width: 228px;
    width: 100%;
    background-color: #232323;
    min-height: 147px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-image: url("@/assets/images/info.svg");
    background-size: 30px 30px;
    background-position: bottom -1px right -1px;
    background-repeat: no-repeat;

    span {
      font-weight: 800;
      font-size: 25px;
      line-height: 35px;
      color: white;
      max-width: 160px;
      text-transform: uppercase;
    }

    @media (max-width: 1023px) {
      min-height: 89px;
      max-width: 138px;
      left: -28px;
      top: -33px;
      background-size: 20px 20px;

      span {
        font-size: 15px;
        line-height: 21px;
        max-width: 90px;
      }
    }
  }
}

.mb-btn {
  max-width: 172px;
  width: 100%;
  display: none;

  @media (max-width: 1023px) {
    display: block;
    margin: 36px auto 0;
  }
}
</style>
