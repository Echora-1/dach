<template>
  <header :class="['header', { scroll: scroll }]">
    <div class="container header__container">
      <icon-logo />
      <div class="header__social">
        <a href=""><IconInst /></a>
        <a href=""><IconWhat /></a>
        <a href=""><IconFace /></a>
      </div>
      <a href="" class="header__phone"><icon-phone /> +380-xxx-xx-xx-xx</a>
      <base-button class="header__btn">
        {{ $t("Заказать обратный звонок") }}
      </base-button>
      <menu-button
        class="header__menu-open"
        @click="showMenu = !showMenu"
        :open="false"
      />
      <base-language-selection
        class="base-header__language"
        :id="'language'"
        :label="'select language'"
        :list="languages"
        item-key="language"
        :default-value="languages[0]"
        @selected="setLocale"
      />
      <nav :class="['header__nav', { 'header__nav--open': showMenu }]">
        <menu-button
          class="header__menu-close"
          @click="showMenu = !showMenu"
          :open="true"
        />
        <ul class="header__nav-list"></ul>
      </nav>
    </div>
  </header>
</template>
<script>
import IconLogo from "../icon/IconLogo.vue";
import MenuButton from "../common/MenuButton.vue";
import BaseButton from "@/components/base/BaseButton.vue";
import IconPhone from "@/components/icon/IconPhone.vue";
import BaseLanguageSelection from "@/components/base/BaseLanguageSelection.vue";
import IconInst from "@/components/icon/IconInst.vue";
import IconWhat from "@/components/icon/IconWhat.vue";
import IconFace from "@/components/icon/IconFace.vue";
export default {
  components: {
    IconFace,
    IconWhat,
    IconInst,
    BaseLanguageSelection,
    IconPhone,
    BaseButton,
    MenuButton,
    IconLogo,
  },

  data() {
    return {
      showMenu: false,
      languages: [
        { language: "RU", id: 1, value: "ru" },
        { language: "UA", id: 2, value: "ua" },
      ],
      currentLanguage: "",
      scroll: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.scrollHeader);
  },

  methods: {
    setLocale(locale) {
      this.$i18n.locale = locale.value;
    },

    scrollHeader() {
      if (window.scrollY >= 80) {
        this.scroll = true;
      } else {
        this.scroll = false;
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.header {
  z-index: 10;
  display: flex;
  align-items: center;
  min-height: 55px;
  position: fixed;
  top: 35px;
  width: 100%;
  padding-top: 10px;
  padding-bottom: 10px;
  background: white;

  &__container {
    display: flex;
    align-items: center;
    max-width: 1400px;
  }

  &__nav {
    position: fixed;
    top: 0;
    right: 0;
    max-width: 410px;
    width: 100%;
    min-height: 100vh;
    background: white;
    transform: translateX(200%);
    transition: all 0.3s;
    padding: 36px 75px 86px 0;
    display: flex;
    flex-direction: column;
    box-shadow: 0 12px 42px rgba(0, 0, 0, 0.16);

    &--open {
      transform: translateX(0);
    }
  }

  &__phone {
    display: flex;
    align-items: center;
    font-size: 20px;
    line-height: 30px;
    margin: 0 40px 0 24px;
    svg {
      color: var(--primary);
      margin-right: 16px;
    }
  }

  &__btn {
    margin-right: 40px;
    background: #232323;
    font-weight: 400;
    font-size: 14px;
    line-height: 15px;
    text-transform: none;
    padding: 15px 20px;
  }

  &__menu-open {
    margin-right: 38px;
  }

  &__menu-close {
    margin-left: auto;
  }

  &__social {
    display: flex;
    align-items: center;
    margin-left: auto;

    a {
      margin-left: 24px;
      color: var(--primary);
      display: flex;

      svg {
        width: 28px;
        height: 28px;
      }
    }
  }
}

.scroll {
  top: 0;
}
</style>
