<template>
  <li class="form__list-item">
    <base-form-input
      input-name="name"
      input-type="text"
      label-text="Имя"
    />
    <base-form-input
      input-name="age"
      input-type="number"
      label-text="Возраст"
    />
    <base-button
      class-name="button_delete"
      name-button="delete button"
      type-button="button"
      @click="$emit('clickDeleteButton')"
    >
      Удалить
    </base-button>
  </li>
</template>

<script>
import BaseButton from './BaseButton.vue';
import BaseFormInput from './BaseFormInput.vue';

export default {
  components: {
    BaseFormInput,
    BaseButton,
  },

};
</script>

<style lang="scss" scoped>

.form__list-item {
  @include flexible();
  gap: 10px 18px;
  align-items: center;
  flex-grow: 1;
}

</style>
