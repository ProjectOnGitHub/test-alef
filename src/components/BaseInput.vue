<template>
  <label class="form__label">
    {{ labelText }}
    <input
      :type="inputType"
      :name="`input-${inputName}`"
      :class="className"
      class="form__input"
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

    className: {
      type: String,
      default: '',
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
