<template>
  <div class="form">
    <form class="form__form" v-if="!loading && !success" @submit.prevent="send">
      <div>
        <base-input
          v-model="form.name"
          type="name"
          id="name"
          name="name"
          class="form__input input"
          label="Имя"
          placeholder="Имя"
          :error-list="nameErrors"
        />
        <base-input
          v-model="form.email"
          id="email"
          name="email"
          class="form__input"
          label="Контактный телефон"
          placeholder="Контактный телефон"
          :error-list="emailErrors"
        />
      </div>
      <base-input
        textarea
        rows="5"
        v-model="form.message"
        type="message"
        id="message"
        name="message"
        class="form__input textarea"
        label="Комментарий"
        placeholder="Комментарий"
        :error-list="messageErrors"
      />
      <base-button class="form__btn" type="submit" :disabled="!formIsValid">
        ОТПРАВИТЬ
      </base-button>
    </form>
    <base-loader v-if="loading && !success" class="form__loader" />
    <icon-form-success v-if="success" width="250" height="250" />
  </div>
</template>

<script>
import BaseInput from "@/components/base/BaseInput";
import BaseButton from "@/components/base/BaseButton";
import BaseLoader from "@/components/base/BaseLoader";
import IconFormSuccess from "@/components/icon/IconFormSuccess";
export default {
  components: { IconFormSuccess, BaseLoader, BaseButton, BaseInput },
  data() {
    return {
      loading: false,
      success: false,
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },

  computed: {
    nameErrors() {
      const errors = [];
      if (!this.form.name.length > 0) errors.push("Обязательное поле");
      return errors;
    },
    emailErrors() {
      const errors = [];
      if (!this.form.email.length > 0) errors.push("Обязательное поле");
      return errors;
    },
    messageErrors() {
      const errors = [];
      if (!this.form.message.length > 0) errors.push("Обязательное поле");
      return errors;
    },

    formIsValid() {
      return (
        this.nameErrors.length === 0 &&
        this.emailErrors.length === 0 &&
        this.messageErrors.length === 0
      );
    },
  },

  methods: {
    send() {
      if (this.formIsValid) {
        this.loading = true;
        setTimeout(() => {
          this.loading = false;
          this.success = true;
        }, 1500);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  display: flex;
  justify-content: center;
  min-height: 164px;

  &__form {
    width: 100%;
    display: flex;
    align-items: center;
    max-width: 1200px;
    justify-content: space-between;
    margin-right: auto;
  }

  &__input {
    max-width: 224px;
    width: 100%;
  }

  &__btn {
    margin-bottom: auto;
    max-width: 278px;
    width: 100%;
  }

  &__loader {
    margin: auto;
  }
}

.input {
  margin-bottom: 46px;
}

.textarea {
  max-width: 420px;

  &:deep {
    .invalid-text {
      bottom: -22px;
    }
  }
}
</style>
