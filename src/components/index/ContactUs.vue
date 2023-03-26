<template>
  <section class="container section-wrap">
    <div class="contact">
      <h2 class="base-title">Contact Us</h2>
      <div class="contact__wrap">
        <div class="contact__left">
          <div class="contact__item">
            <p class="contact__key">email</p>
            <p class="contact__value">hello@uxwizards.studio</p>
          </div>
          <div class="contact__item">
            <p class="contact__key">phone number</p>
            <p class="contact__value">+1 758 475 743</p>
          </div>
          <div class="contact__item">
            <p class="contact__key">telegram</p>
            <p class="contact__value">@uxwizards.studio</p>
          </div>
        </div>
        <div class="content__right">
          <contact-form />
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.contact {
  width: 945px;

  .base-title {
    margin: 0 0 52px;
  }

  &__wrap {
    display: flex;
    align-items: center;
  }

  &__left {
    max-width: 215px;
    width: 100%;
    margin-right: 64px;
  }

  &__right {
  }

  &__item {
    display: flex;
    flex-direction: column;

    &:not(:last-child) {
      margin-bottom: 71px;
    }
  }

  &__key {
    font-weight: 600;
    font-size: 15px;
    line-height: 115%;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: rgba(0, 0, 0, 0.6);
    margin: 0 0 10px;
  }

  &__value {
    font-weight: 500;
    font-size: 15px;
    line-height: 115%;
    letter-spacing: 0.05em;
    margin: 0;
  }
}
</style>
<script>
import ContactForm from "@/components/index/ContactForm";
export default {
  components: { ContactForm },
};
</script>
