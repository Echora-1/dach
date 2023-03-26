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
}

.portfolio {
  padding-bottom: 177px;
  display: flex;
  justify-content: space-between;

  &__left {
    max-width: 400px;
    width: 100%;

    p {
      max-width: 362px;
      font-size: 20px;
      line-height: 30px;
      margin: 27px 0 65px;
    }
  }
  &__right {
    margin-left: 40px;
    margin-right: 40px;
    max-width: 594px;
    position: relative;

    &::before {
      content: "";
      position: absolute;
      width: 176px;
      height: 173px;
      border: 1px solid #bbbbbb;
      right: -39px;
      bottom: -77px;
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
      }

      .swiper-button-next {
        background: url("@/assets/images/swiperBtn.svg") no-repeat center;
        transform: scale(-1);
        border: none;
        right: -40px;

        &::after {
          display: none;
        }
      }
    }
  }

  &__btn {
    max-width: 278px;
    width: 100%;
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
    }
  }
}
</style>
