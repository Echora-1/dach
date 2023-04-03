<template>
  <header :class="['header']">
    <div class="container header__container">
      <icon-logo class="header__logo" />
      <div class="header__social">
        <a href=""><IconInst /></a>
        <a href=""><IconWhat /></a>
        <a href=""><IconFace /></a>
      </div>
      <a href="" class="header__phone"
        ><icon-phone /> <span>+380-xxx-xx-xx-xx</span></a
      >
      <base-button class="header__btn">
        {{ $t("Заказать обратный звонок") }}
      </base-button>
      <menu-button
        class="header__menu-open"
        @click="showMenu = !showMenu"
        :open="false"
        @mouseover="show = true"
        @mouseleave="show = false"
      >
        <nav-list @mouseover="show = true" v-if="show" class="nav-list" />
      </menu-button>
      <base-language-selection
        class="header__language"
        :id="'language'"
        :label="'select language'"
        :list="languages"
        item-key="language"
        :default-value="languages[0]"
        @selected="setLocale"
      />
      <nav
        @click="showMenu = false"
        :class="['header__nav', { 'header__nav--open': showMenu }]"
      >
        <div class="header__nav-wrap" @click.stop="">
          <div class="header__nav-header">
            <menu-button
              class="header__nav-btn"
              @click="showMenu = !showMenu"
              :open="showMenu"
            />

            <icon-logo class="header__mb-logo" />
          </div>
          <nav-list @click="showMenu = false" />
          <div class="header__nav-social">
            <a href=""><IconInst /></a>
            <a href=""><IconWhat /></a>
            <a href=""><IconFace /></a>
          </div>
        </div>
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
import NavList from "@/components/base/NavList.vue";
export default {
  components: {
    NavList,
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
      show: true,
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
  background-color: #f3f3f3;

  @media (max-width: 1023px) {
    border-bottom: 1px solid #e2e2e2;
  }

  &__logo {
    @media (max-width: 1023px) {
      height: 28px;
      width: 178px;
    }
  }

  &__container {
    display: flex;
    align-items: center;
    max-width: 1400px;
    width: 100%;
    padding-top: 47px;

    @media (max-width: 1023px) {
      padding-top: 25px;
      padding-bottom: 25px;
    }
  }

  &__nav {
    position: fixed;
    top: 0;
    right: 0;
    width: 100%;
    transform: translateX(200%);
    transition: all 0.3s;
    flex-direction: column;
    display: none;
    min-height: 100vh;
    z-index: 10;
    background: rgba(0, 0, 0, 0.6);

    @media (max-width: 1023px) {
      &--open {
        transform: translateX(0);
        display: flex;
      }
    }
  }

  &__nav-wrap {
    padding: 36px 75px 86px 0;
    background: #282828;
    max-width: calc(100% - 60px);
    width: 100%;
    min-height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    display: flex;
    flex-direction: column;

    @media (max-width: 1023px) {
      padding: 36px 0;
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
    @media (max-width: 1023px) {
      margin: 0 20px 0 auto;
      span {
        display: none;
      }

      svg {
        width: 21px;
        height: 21px;
        margin-right: 0;
      }
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

    @media (max-width: 1023px) {
      display: none;
    }
  }

  &__menu-open {
    @media (min-width: 1024px) {
      margin-right: 38px;
      overflow: visible;
    }
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
    @media (max-width: 1023px) {
      display: none;
    }
  }
  &__language {
    @media (max-width: 1023px) {
      display: none;
    }
  }

  &__nav-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 45px;
    padding: 0 28px;
  }

  &__mb-logo {
    width: 158px;
    height: 25px;
    color: #ffffff;
  }

  &__nav-social {
    color: var(--primary);
    display: flex;
    justify-content: center;
    gap: 10px;
    margin: auto 0 15px;

    svg {
      width: 29px;
      height: 29px;
    }
  }
}

.scroll {
  top: 0;
}

.nav-list {
  opacity: 1;
  position: absolute;
  bottom: -290px;
  left: -151px;
  min-width: 195px;
  z-index: 3;
  padding-top: 30px;

  @media (max-width: 1023px) {
    display: none;
  }
}
</style>
