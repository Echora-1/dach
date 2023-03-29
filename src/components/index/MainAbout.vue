<template>
  <div class="about container">
    <div class="decor"></div>
    <div class="decor1"></div>
    <div class="decor2"></div>
    <h2 class="base-title">
      {{ $t("Наши") }} <span>{{ $t("преимущества") }}</span>
    </h2>
    <div class="about__list">
      <div class="about__item">
        <icon-about1 />
        <p class="about__item-text">
          {{ $t("Квалифицированные специалисты") }}
        </p>
      </div>
      <div class="about__item">
        <icon-about2 />
        <p class="about__item-text">{{ $t("Соблюдение сроков") }}</p>
      </div>
      <div class="about__item">
        <icon-about3 />
        <p class="about__item-text">{{ $t("Внимание к деталям") }}</p>
      </div>
      <div class="about__item">
        <icon-about4 />
        <p class="about__item-text">{{ $t("Авторское выполнение") }}</p>
      </div>
    </div>
    <div class="about__list2">
      <div class="about__item">
        <icon-about5 />
        <p style="max-width: 207px">
          {{ $t("Правильный расчет услуг и материалов") }}
        </p>
      </div>
      <div class="about__item">
        <icon-about6 />
        <p style="max-width: 322px">
          {{
            $t("Соблюдение технических требований и рекомендаций производителя")
          }}
        </p>
      </div>
      <div class="about__item">
        <icon-about7 />
        <p style="max-width: 215px">
          {{ $t("Выполнение гарантийных обязательств") }}
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.base-title {
  margin: 0 auto 110px;
  text-align: center;

  @media (max-width: 1023px) {
    margin: 0 auto 40px;
  }
}

.about {
  position: relative;
  &__list {
    max-width: 1075px;
    width: 100%;
    margin: 0 auto 124px;
    display: flex;
    justify-content: space-between;

    @media (max-width: 1023px) {
      flex-direction: column;
      justify-content: center;
      margin: 0 auto;
    }
  }

  &__list2 {
    max-width: 970px;
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;

    @media (max-width: 1023px) {
      flex-direction: column;
      justify-content: center;
    }

    p {
      font-weight: 800;
      font-size: 17px;
      line-height: 26px;
      margin: 26px 0 0;

      @media (max-width: 1023px) {
        font-size: 15px;
        line-height: 22px;
        max-width: 250px !important;
      }
    }
  }

  &__item {
    display: flex;
    align-items: center;
    flex-direction: column;
    text-align: center;

    @media (max-width: 1023px) {
      margin-bottom: 36px;
    }
  }

  &__item-text {
    font-weight: 800;
    font-size: 17px;
    line-height: 26px;
    margin: 26px 0 0;
    max-width: 160px;

    @media (max-width: 1023px) {
      font-size: 15px;
      line-height: 22px;
    }
  }

  .decor,
  .decor1,
  .decor2 {
    @media (min-width: 1024px) {
      display: none;
    }
    position: absolute;
    border: 1px solid #e2e2e2;
  }

  .decor {
    width: 100px;
    height: 179px;
    top: 230px;
    right: -20px;
  }

  .decor1 {
    width: 81px;
    height: 127px;
    top: 560px;
    left: -20px;
  }

  .decor2 {
    width: 70px;
    height: 193px;
    top: 870px;
    right: -20px;
  }
}
</style>
<script setup>
import IconAbout1 from "@/components/icon/IconAbout1.vue";
import IconAbout2 from "@/components/icon/IconAbout2.vue";
import IconAbout3 from "@/components/icon/IconAbout3.vue";
import IconAbout4 from "@/components/icon/IconAbout4.vue";
import IconAbout5 from "@/components/icon/IconAbout5.vue";
import IconAbout6 from "@/components/icon/IconAbout6.vue";
import IconAbout7 from "@/components/icon/IconAbout7.vue";
</script>
