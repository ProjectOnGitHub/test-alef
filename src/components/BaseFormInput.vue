<template>
  <label class="form__label">
    {{ labelText }}
    <input
      :type="inputType"
      :name="`input-${inputName}`"
      :value="value"
      :class="className"
      class="form__input"
      v-bind="inputAttributes"
      @input="$emit('input', $event.target.value)"
    />
  </label>
</template>
<script>
export default {
  props: {
    labelText: {
      type: String,
      default: '',
    },
    inputId: {
      type: String,
      default: '',
    },
    inputType: {
      type: String,
      default: '',
    },
    inputName: {
      type: String,
      default: '',
    },
    value: [String, Number],
    className: {
      type: String,
      default: '',
    },
  },
  data() {
    return {
      minLengthValue: 0,
      maxLengthValue: 100,
      minValue: 16,
      maxValue: 100,
    };
  },
  computed: {
    inputAttributes() {
      if (this.inputType === 'text') {
        return {
          minLength: this.minLengthValue,
          maxLength: this.maxLengthValue,
        };
      } if (this.inputType === 'number') {
        return {
          min: this.minValue,
          max: this.maxValue,
        };
      }
      return {};
    },
  },
};
</script>

<style scoped lang="scss">
.form {
  &__label {
    @include flexible();
    flex-direction: column;
    box-sizing: border-box;
    border: 1px solid $colors-gray-l;
    border-radius: 4px;
    padding: 8px 16px;
    color: $colors-gray;
    font-size: 13px;
  }

  &__input {
    padding: 0;
    width: 100%;
    border: none;
    line-height: 1.71;
    box-sizing: border-box;

    &:focus {
      outline: none;
      border-bottom: 1px solid $colors-gray;
    }

  }
}

</style>
