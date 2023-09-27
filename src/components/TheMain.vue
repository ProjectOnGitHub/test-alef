<template>
  <main class="main">
    <div class="main__container">
      <base-form v-if="viewComponent">
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
          <base-button
            class-name="button_add"
            type-button="button"
            @click="addComponent"
          >
            <svg-icon
              icon-name="plus"
              icon-class="plus"
            />
            Добавить
          </base-button>
          <ul
            v-for="(item, index) in inputsList"
            :key="index"
            class="form__list"
          >
            <component
              :is="item"
              @clickDeleteButton="deleteInput(index)"
            />
          </ul>
        </base-form-fieldset>
        <base-button class-name="button_save">
          Сохранить
        </base-button>
      </base-form>
      <person-info v-else />
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
import BaseFormListItem from './BaseFormListItem.vue';

export default {
  components: {
    SvgIcon,
    PersonInfo,
    BaseButton,
    BaseFormFieldset,
    BaseForm,
    BaseFormInput,
    BaseFormListItem,
  },
  props: {
    viewComponent: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      inputsList: [],

    };
  },
  methods: {
    addComponent() {
      if (this.inputsList.length < 5) {
        this.inputsList.push('base-form-list-item');
      }
    },
    deleteInput(index) {
      this.inputsList.splice(index, 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.main {
  @include gridable();
  box-sizing: border-box;
  grid-row: 2;

  &__container {
    @include flexible();
    flex-direction: column;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;
  }
}

</style>
