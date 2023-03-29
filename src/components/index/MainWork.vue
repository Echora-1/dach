<template>
  <div class="work container">
    <h2 class="base-title">
      {{ $t("Как мы") }} <span>{{ $t("работаем") }}</span>
    </h2>
    <div class="work__list">
      <div class="work__item">
        <div class="work__item-header">
          <span> 01 </span>
          <p>{{ $t("Звонок или заявка") }}</p>
        </div>
        <p class="work__item-text">
          {{ $t("Все заявки обрабатываются в течении 24 часов") }}
        </p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 02 </span>
          <p>{{ $t("Замеры и расчет") }}</p>
        </div>
        <p class="work__item-text">
          {{
            $t(
              " Наш сотрудник выезжает к вам на объект и делает необходимые замеры либо делаем расчет согласно проекту"
            )
          }}
        </p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 03 </span>
          <p>{{ $t("Согласование деталей") }}</p>
        </div>
        <p class="work__item-text">
          {{ $t("Обсуждаем все детали") }}
        </p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 04 </span>
          <p>{{ $t("Подписание договора") }}</p>
        </div>
        <p class="work__item-text"></p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 05 </span>
          <p>{{ $t("Доставка материалов на объект") }}</p>
        </div>
        <p class="work__item-text">
          {{ $t("Доставка материалов") }}
        </p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 06 </span>
          <p>{{ $t("Выполнение оговоренных работ") }}</p>
        </div>
        <p class="work__item-text"></p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 07 </span>
          <p>{{ $t("Сдача/прием работы") }}</p>
        </div>
        <p class="work__item-text"></p>
      </div>
      <div class="work__item">
        <div class="work__item-header">
          <span> 08 </span>
          <p>{{ $t("Расчет") }}</p>
        </div>
        <p class="work__item-text">
          {{ $t("Окончательная оплата") }}
        </p>
      </div>
      <div class="work__finish">
        <p>
          <span>{{ $t("Поздравляем") }}</span> <br />{{ $t("Идеальная") }}
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.base-title {
  text-align: center;
  margin: 0 0 167px;
  padding-bottom: 40px;
  position: relative;

  &::before {
    content: "";
    width: 63%;
    max-width: 818px;
    height: 1px;
    background: rgba(184, 184, 184, 1);
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
  }

  @media (max-width: 1023px) {
    margin: 0 auto 98px;
    max-width: 330px;

    &::before {
      max-width: 142px;
    }
  }
}

.work {
  &__list {
    height: 1230px;
    width: 100%;
    position: relative;
    max-width: 882px;
    margin: 0 auto;

    &::before {
      position: absolute;
      content: "";
      width: 25px;
      height: 1121px;
      background-image: url("@/assets/images/line.svg");
      background-position: center;
      background-repeat: no-repeat;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      z-index: 1;
    }

    @media (max-width: 1023px) {
      max-width: 335px;
      height: 1125px;

      &::before {
        background-image: url("@/assets/images/mb-line.svg");
        width: 10px;
        height: 1053px;
      }
    }
  }

  &__item {
    max-width: 441px;

    @media (max-width: 1023px) {
      max-width: 50%;
    }

    &:hover {
      span {
        color: var(--primary);
      }
    }

    &:nth-child(odd) {
      margin-right: auto;

      @media (max-width: 1023px) {
        .work__item-text {
          padding-right: 15px;
        }
      }
    }

    &:nth-child(even) {
      margin-left: auto;

      .work__item-header {
        @media (min-width: 1024px) {
          padding-left: 27px;
        }

        @media (max-width: 1023px) {
          span {
            left: unset;
            right: 0;
          }

          padding-left: 25px;
        }
      }

      .work__item-text {
        @media (min-width: 1024px) {
          margin-left: 27px;
        }

        @media (max-width: 1023px) {
          padding-left: 25px;
        }
      }
    }
    &:nth-child(1) {
      transform: translateY(-95px);
    }

    &:nth-child(2) {
      transform: translateY(-210px);
    }

    &:nth-child(3) {
      transform: translateY(-325px);
    }

    &:nth-child(4) {
      transform: translateY(-440px);
    }

    &:nth-child(5) {
      transform: translateY(-555px);
    }

    &:nth-child(6) {
      transform: translateY(-670px);
    }

    &:nth-child(7) {
      transform: translateY(-785px);
    }

    &:nth-child(8) {
      transform: translateY(-900px);
    }

    @media (max-width: 1023px) {
      &:nth-child(1) {
        transform: translateY(-70px);
      }

      &:nth-child(2) {
        transform: translateY(-140px);
      }

      &:nth-child(3) {
        transform: translateY(-228px);
      }

      &:nth-child(4) {
        transform: translateY(-298px);
      }

      &:nth-child(5) {
        transform: translateY(-367px);
      }

      &:nth-child(6) {
        transform: translateY(-455px);
      }

      &:nth-child(7) {
        transform: translateY(-524px);
      }

      &:nth-child(8) {
        transform: translateY(-594px);
      }
    }
  }

  &__item-header {
    display: flex;
    border-bottom: 1px solid #b8b8b8;
    position: relative;
    min-height: 75px;
    span {
      font-weight: 700;
      font-size: 120px;
      line-height: 115px;
      margin-bottom: -8px;
      color: #f2f2f2;
      transition: color 0.3s;

      @media (max-width: 1023px) {
        font-size: 79px;
        line-height: 75px;
        margin-bottom: -5px;
        position: absolute;
        bottom: 0;
        left: 0;
      }
    }

    p {
      align-self: center;
      display: inline-block;
      margin: 0 0 0 44px;
      font-weight: 800;
      font-size: 22px;
      line-height: 30px;
      max-width: 180px;

      @media (max-width: 1023px) {
        font-size: 15px;
        line-height: 20px;
        margin: 0;
        position: relative;
        z-index: 1;
        max-width: 125px;
      }
    }
  }

  &__item-text {
    font-size: 20px;
    line-height: 27px;
    max-width: 367px;
    min-height: 107px;

    @media (max-width: 1023px) {
      font-size: 14px;
      line-height: 18px;
      margin: 18px 0 0;
      max-height: 126px;
    }
  }

  &__finish {
    border: 1px solid var(--primary);
    padding: 27px 32px;
    transform: translateY(-926px);
    max-width: 475px;
    margin: 0 auto;
    position: relative;
    z-index: 2;

    p {
      margin: 0;
      text-align: center;
      font-weight: 500;
      font-size: 20px;
      line-height: 28px;
    }

    span {
      font-weight: 800;
    }

    @media (max-width: 1023px) {
      transform: translateY(-590px);
      padding: 17px 15px;

      p {
        font-size: 14px;
        line-height: 18px;
      }

      span {
        font-weight: 800;
      }
    }
  }
}
</style>
