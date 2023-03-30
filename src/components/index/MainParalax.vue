<template>
  <div class="para" ref="para">
    <div class="para__wrap container">
      <div class="para__item">
        <span>18</span>
        <p>лет безупречного опыта</p>
      </div>
      <div class="line"></div>
      <div class="para__item">
        <span>420 </span>
        <p>выполненных объектов</p>
      </div>
      <div class="line"></div>
      <div class="para__item">
        <span>10</span>
        <p>лет гарантии</p>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

export default {
  mounted() {
    const element = this.$refs.para;
    gsap.registerPlugin(ScrollTrigger);
    ScrollTrigger.create({
      trigger: element,
      start: "top top",
      end: "bottom top",
      pin: true,
      pinSpacing: false,
      scrub: true,
    });
  },

  unmounted() {
    ScrollTrigger.kill();
  },
};
</script>

<style lang="scss" scoped>
.para {
  background-image: url("@/assets/images/paralaxbg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  min-height: 307px;
  display: flex;
  justify-content: center;
  align-items: center;

  @media (max-width: 1023px) {
    min-height: 176px;
    background-image: url("@/assets/images/mb-paralaxbg.png");
  }

  &__wrap {
    max-width: 1000px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;

    span {
      font-weight: 700;
      font-size: 133.854px;
      line-height: 183px;
      text-align: center;
      color: var(--primary);

      @media (max-width: 1023px) {
        font-size: 53px;
        line-height: 72px;
      }
    }

    p {
      margin: 0;
      font-size: 20px;
      line-height: 30px;
      color: #ffffff;
      max-width: 228px;
      text-align: center;
      min-height: 60px;

      @media (max-width: 1023px) {
        font-size: 13px;
        line-height: 17px;
        max-width: 92px;
      }
    }
  }

  &__item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .line {
    width: 1px;
    background: rgba(255, 255, 255, 0.5);
    height: 170px;

    @media (max-width: 1023px) {
      height: 60px;
    }
  }
}
</style>
