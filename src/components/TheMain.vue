<template>
  <main class="main">
    <div class="main__container">
      <base-form>
        <base-form-fieldset
          title="Персональные данные"
        >
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
        </base-form-fieldset>
        <base-form-fieldset
          title="Дети (макс. 5)"
          class="form__fieldset_row"
        >
          <base-button class-name="button_add">
            <svg-icon
              icon-name="plus"
              icon-class="plus"
            />
            Добавить
          </base-button>
          <div class="form__fieldset-container">
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
            <base-button class-name="button_delete">
              Удалить
            </base-button>
          </div>
        </base-form-fieldset>

        <base-button class-name="button_save">
          Сохранить
        </base-button>
      </base-form>

      <person-info />
    </div>
  </main>
</template>

<script>

import BaseForm from './BaseForm.vue';
import BaseFormFieldset from './BaseFormFieldset.vue';
import BaseFormInput from './BaseFormInput.vue';
import BaseButton from './BaseButton.vue';
import PersonInfo from './PersonInfo.vue';
import SvgIcon from './SvgIcon.vue';

export default {
  components: {
    SvgIcon,
    PersonInfo,
    BaseButton,
    BaseFormFieldset,
    BaseForm,
    BaseFormInput,
  },

};
</script>

<style lang="scss" scoped>
.main {
  @include gridable();
  box-sizing: border-box;

  &__container {
    @include flexible();
    flex-direction: column;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;
  }
}

</style>
