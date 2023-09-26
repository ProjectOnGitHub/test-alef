<template>
  <form class="form">
    <fieldset class="form__fieldset">
      <legend class="form__fieldset-legend">
        Персональные данные
      </legend>
      <base-input
        label-text="Имя"
        input-type="text"
        input-name="name"
      />
      <base-input
        label-text="Возраст"
        input-type="number"
        input-name="age"
      />
    </fieldset>
  </form>
</template>

<script>
import BaseInput from './BaseInput.vue';

export default {
  components: { BaseInput },

};
</script>

<style lang="scss" scoped>

.form {
  @include flexible();
  flex-direction: column;
  max-width: 616px;
  box-sizing: border-box;

  &__fieldset {
    @include flexible();
    flex-direction: column;
    border: none;
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    gap: 10px;

    &-legend {
      color: $colors-black;
      font-size: 16px;
      font-style: normal;
      font-weight: 500;
      line-height: 1.5;
      box-sizing: border-box;
      padding: 10px 0;
    }
  }

}

</style>
