<template>
  <fieldset
    class="form__fieldset"
    :class="className"
  >
    <h2 class="form__fieldset-title">
      {{ title }}
    </h2>
    <slot>
    </slot>
  </fieldset>
</template>
<script>
export default {
  props: {
    title: {
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
<style lang="scss" scoped>
.form {
  &__fieldset {
    @include flexible();
    flex-direction: column;
    border: none;
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    gap: 10px 18px;

    &_row {
      flex-direction: row;
      flex-grow: 0;
      flex-wrap: wrap;
      align-items: center;
    }

    &-container {
      @include flexible();
      gap: 10px 18px;
      align-items: center;
      flex-grow: 1;
    }

    &-title {
      color: $colors-black;
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 1.5;
      box-sizing: border-box;
      padding: 10px 0;
      margin: 0;
      flex-grow: 1
    }
  }
}
</style>
