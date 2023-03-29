<template>
  <div>
    <MainScreen />
    <MainServices class="section-services" />
    <MainAbout class="section-about" />
    <MainWork class="section-work" />
    <MainPortfolio class="section-portfolio" />
    <MainParalax />
    <MainContact />
  </div>
</template>

<script>
import MainScreen from "@/components/index/MainScreen";
import MainServices from "@/components/index/MainServices.vue";
import MainAbout from "@/components/index/MainAbout.vue";
import MainWork from "@/components/index/MainWork.vue";
import MainPortfolio from "@/components/index/MainPortfolio.vue";
import MainParalax from "@/components/index/MainParalax.vue";
import MainContact from "@/components/index/MainContact.vue";
export default {
  components: {
    MainContact,
    MainParalax,
    MainPortfolio,
    MainWork,
    MainAbout,
    MainServices,
    MainScreen,
  },
};
</script>

<style lang="scss" scoped>
.section-services {
  padding-top: 108px;
  padding-bottom: 114px;

  @media (max-width: 1023px) {
    padding-top: 52px;
    padding-bottom: 54px;
  }
}

.section-about {
  padding-bottom: 135px;
  position: relative;

  &::before {
    content: "";
    width: 83%;
    max-width: 1190px;
    height: 1px;
    background: #b8b8b8;
    position: absolute;
    left: 50%;
    bottom: 0;
    transform: translateX(-50%);
  }

  @media (max-width: 1023px) {
    padding-bottom: 20px;

    &::before {
      max-width: 142px;
    }
  }
}

.section-work {
  padding-top: 44px;
  padding-bottom: 168px;

  @media (max-width: 1023px) {
    padding-top: 40px;

    padding-bottom: 73px;
  }
}
</style>
