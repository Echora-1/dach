<template>
  <div class="about container">
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
}

.about {
  &__list {
    max-width: 1075px;
    width: 100%;
    margin: 0 auto 124px;
    display: flex;
    justify-content: space-between;
  }

  &__list2 {
    max-width: 970px;
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;

    p {
      font-weight: 800;
      font-size: 17px;
      line-height: 26px;
      margin: 26px 0 0;
    }
  }

  &__item {
    display: flex;
    align-items: center;
    flex-direction: column;
    text-align: center;
  }

  &__item-text {
    font-weight: 800;
    font-size: 17px;
    line-height: 26px;
    margin: 26px 0 0;
    max-width: 160px;
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
