<template>
  <div class="contact">
    <div class="contact__wrap container">
      <h2 class="base-title mb-title">{{ $t("Контакты") }}</h2>
      <ContactMap class="contact__map" />
      <div class="contact__info">
        <h2 class="base-title">{{ $t("Контакты") }}</h2>

        <div class="contact__list">
          <a href=""><IconHome />Адрес компании</a>
          <a href=""><IconPhone />+380-xxx-xx-xx-xx</a>
          <a href=""><IconMessage />companyname@gmail.com</a>
        </div>
        <div class="contact__social">
          <p>Свяжитесь с нами:</p>
          <a href=""><IconInst /></a>
          <a href=""><IconWhat /></a>
          <a href=""><IconFace /></a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.base-title {
  margin-bottom: 56px;
  max-width: 450px;
  position: relative;
  display: none;

  @media (min-width: 1024px) {
    display: block;
    &::before {
      content: "";
      position: absolute;
      width: 76px;
      height: 1px;
      background: #b8b8b8;
      right: 30px;
      top: 60%;
      transform: translateY(-50%);
    }
  }
}

.mb-title {
  display: none;
  margin-bottom: 35px;

  @media (max-width: 1023px) {
    display: block;
  }
}

.contact {
  width: 100%;
  background: #ffffff;
  position: relative;
  z-index: 2;
  padding: 144px 0 160px;

  @media (max-width: 1023px) {
    padding: 54px 0 60px;
  }

  &__map {
    max-width: 675px;
    position: relative;

    @media (min-width: 1024px) {
      &::before {
        content: "";
        position: absolute;
        left: -44px;
        top: -48px;
        width: 176px;
        height: 173px;
        border: 1px solid #bbbbbb;
      }
    }
  }

  &__info {
    flex-grow: 1;

    @media (min-width: 1024px) {
      margin-left: 70px;
    }
  }

  &__wrap {
    display: flex;
    align-items: center;

    @media (max-width: 1023px) {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  }

  &__list {
    display: flex;
    flex-direction: column;
    border-bottom: 1px solid #b8b8b8;
    max-width: 386px;
    margin-bottom: 22px;

    @media (max-width: 1023px) {
      margin-top: 35px;
      border-bottom: 0;
      position: relative;

      &::before {
        content: "";
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translateX(-50%);
        width: 182px;
        height: 1px;
        background: rgba(184, 184, 184, 1);
      }
    }

    a {
      margin-bottom: 30px;
      font-size: 20px;
      line-height: 30px;
      display: flex;
      align-items: center;

      @media (max-width: 1023px) {
        flex-direction: column;
        font-size: 14px;
        line-height: 30px;
        margin-bottom: 20px;
      }
    }

    svg {
      color: var(--primary);

      @media (min-width: 1024px) {
        margin-right: 30px;
      }

      @media (max-width: 1023px) {
        margin-bottom: 9px;
      }
    }
  }

  &__social {
    display: flex;
    align-items: center;
    max-width: 386px;

    p {
      font-weight: 500;
      font-size: 20px;
      line-height: 30px;
      margin: 0 auto 0 0;
    }

    a {
      margin-left: 30px;
      color: var(--primary);
    }

    @media (max-width: 1023px) {
      margin-top: 20px;
      p {
        display: none;
      }

      a:nth-child(2) {
        margin-left: 0;
      }
    }
  }
}
</style>
<script setup>
import ContactMap from "@/components/index/ContactMap.vue";
import IconHome from "@/components/icon/IconHome.vue";
import IconPhone from "@/components/icon/IconPhone.vue";
import IconMessage from "@/components/icon/IconMessage.vue";
import IconInst from "@/components/icon/IconInst.vue";
import IconWhat from "@/components/icon/IconWhat.vue";
import IconFace from "@/components/icon/IconFace.vue";
</script>
