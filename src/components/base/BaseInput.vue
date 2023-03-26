<template>
  <div
    :class="['wrap', { 'input-focused': focused, invalid: touched && invalid }]"
  >
    <label :for="id" :class="['base-label']">
      {{ label }}
    </label>
    <div class="base-input-wrapper">
      <template v-if="textarea">
        <textarea
          :id="id"
          class="base-input"
          v-bind="$attrs"
          :placeholder="$attrs.placeholder"
          :value="modelValue"
          @focus="focusHandler"
          @input="inputHandler"
          @blur="blurHandler"
        />
      </template>
      <template v-else>
        <input
          :id="id"
          class="base-input"
          v-bind="$attrs"
          :placeholder="$attrs.placeholder"
          :value="modelValue"
          @focus="focusHandler"
          @input="inputHandler"
          @blur="blurHandler"
        />
      </template>
    </div>
    <p v-show="touched && invalid" class="invalid-text">{{ errorList[0] }}</p>
  </div>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      default: "",
    },

    id: {
      type: String,
      default: "",
    },

    label: {
      type: String,
      default: "",
    },

    errorList: {
      type: Array,
      default: () => [],
    },
    textarea: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {
      focused: false,
      touched: false,
    };
  },

  computed: {
    invalid() {
      return this.errorList.length > 0;
    },
  },

  methods: {
    inputHandler(event) {
      this.$emit("update:modelValue", event.target.value);
    },

    focusHandler() {
      this.focused = true;
    },

    blurHandler() {
      this.touched = true;
      this.focused = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.wrap {
  position: relative;
}

.base-input-wrapper {
  border-bottom: 1px solid rgb(255, 255, 255);
  width: 100%;
  transition: all 0.5s;
  position: relative;
  margin-bottom: 18px;
  overflow: hidden;
}

.base-input {
  width: 100%;
  margin: 0;
  border: none;
  outline: none;
  padding: 14px 14px 12px 0;
  background: transparent;
  font-weight: 300;
  font-size: 20px;
  color: rgba(255, 255, 255, 0.6);
  -webkit-box-shadow: inset 0 0 0 50px #1f1f1f;
  -webkit-text-fill-color: rgba(255, 255, 255, 0.6);
  position: relative;
  transition: color 0.3s;
  resize: none;

  @media (max-width: 767px) {
    padding: 10px 20px;
  }

  &:-webkit-autofill,
  &:-webkit-autofill:hover,
  &:-webkit-autofill:focus {
    background-color: #1f1f1f !important;
    background-image: none !important;
    color: #fff !important;
  }
}

.base-input::placeholder {
  color: rgba(255, 255, 255, 0.6);
}

.base-label {
  display: none;

  &--show {
    opacity: 1;
  }
}

.input-focused {
  .base-input-wrapper {
    border-color: #ffffff;
  }

  .base-input {
    -webkit-text-fill-color: #ffffff !important;
  }
}

.invalid {
  .base-input-wrapper {
    border-color: #db0d00;
  }
}

.invalid-text {
  color: #db0d00;
  position: absolute;
  bottom: -40px;
  left: 0;
  font-size: 13px;
  line-height: 19px;
}
</style>
