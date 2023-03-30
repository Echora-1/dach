<template>
  <footer class="footer">
    <div class="container">
      <h2 class="base-title">
        {{ $t("Обсудим") }}
        <span>{{ $t("ваш проект?") }}</span>
        <IconDecorArrow />
      </h2>
      <contact-form />
      <div class="footer__info">
        <div>
          <p>Поддержка клиентов:</p>
          <a style="margin: 0" href="">+380-xxx-xx-xx-xx</a>
        </div>

        <div>
          <p>Присоединяйтесь:</p>
          <div>
            <a href=""><IconInst /></a>
            <a href=""><IconWhat /></a>
            <a href=""><IconFace /></a>
          </div>
        </div>

        <div>
          <p>Офис:</p>
          <span>Адрес офиса</span>
        </div>

        <IconLogo />
      </div>
      <div class="footer__info-text">
        <p>Договор оферты</p>
        <div></div>
        <p>Политика конфиденциальности</p>
      </div>
      <p class="footer__copir">ООО «НАЗВАНИЕ» © 2023г.</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.base-title {
  color: #ffffff;
  font-weight: 700;
  font-size: 65px;
  line-height: 121.26%;
  margin-bottom: 50px;

  svg {
    margin-left: 20px;
    transform: scale(-1, -1);
  }

  @media (max-width: 1023px) {
    font-weight: 700;
    font-size: 40px;
    line-height: 45px;
    text-align: center;
    max-width: 266px;
    margin: 0 auto 40px;

    svg {
      display: none;
    }
  }
}

.container {
  @media (max-width: 1023px) {
    display: flex;
    flex-direction: column;
  }
}

.footer {
  background: #1f1f1f;
  padding: 60px 0 50px;

  @media (max-width: 1023px) {
    display: flex;
    flex-direction: column;
    padding: 44px 0 30px;
  }

  &__info {
    margin-top: 80px;
    margin-bottom: 60px;
    color: white;
    display: flex;
    justify-content: space-between;
    text-align: center;

    @media (max-width: 1023px) {
      display: flex;
      flex-direction: column;
      margin-top: 50px;
      margin-bottom: 40px;
      align-items: center;

      & > div:nth-child(2) {
        order: 1;
        margin-top: 22px;
        margin-bottom: 40px;
      }

      & > div:nth-child(3) {
        margin-top: 22px;
      }
      svg {
        order: 2;
      }
    }

    p {
      font-weight: 600;
      font-size: 21px;
      line-height: 130%;
      margin: 0 0 13px;

      @media (max-width: 1023px) {
        font-size: 18px;
        line-height: 130%;
        margin: 0 auto 13px;
        text-align: center;
      }
    }

    a,
    span {
      font-weight: 300;
      font-size: 21px;
      line-height: 130%;

      @media (max-width: 1023px) {
        font-size: 18px;
        line-height: 130%;
        display: inline-flex;
        margin: 0 auto;
        text-align: center;

        svg {
          width: 29px;
          height: 29px;
        }
      }
    }

    a:not(:first-child) {
      margin-left: 24px;
    }
  }

  &__info-text {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 auto 11px;
    max-width: 485px;
    color: var(--primary);

    p {
      font-size: 18px;
      line-height: 124%;
      margin: 0;
    }

    div {
      width: 1px;
      height: 21px;
      background: var(--primary);
    }

    @media (max-width: 1023px) {
      display: flex;
      flex-direction: column;

      p {
        font-size: 13px;
        line-height: 124%;
      }

      div {
        display: none;
      }
    }
  }

  &__copir {
    font-weight: 300;
    font-size: 18px;
    line-height: 124%;
    color: white;
    display: block;
    margin: 0 auto;
    text-align: center;

    @media (max-width: 1023px) {
      font-size: 13px;
      line-height: 124%;
    }
  }
}
</style>
<script setup>
import IconDecorArrow from "@/components/icon/IconDecorArrow.vue";
import ContactForm from "@/components/index/ContactForm.vue";
import IconLogo from "@/components/icon/IconLogo.vue";
import IconInst from "@/components/icon/IconInst.vue";
import IconWhat from "@/components/icon/IconWhat.vue";
import IconFace from "@/components/icon/IconFace.vue";
</script>
