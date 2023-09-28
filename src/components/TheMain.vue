<template>
  <main class="main">
    <div class="main__container">
      <base-form v-if="viewComponent">
        <base-form-fieldset
          title="Персональные данные"
        >
          <base-form-input
            v-model="personName"
            input-name="name"
            input-type="text"
            label-text="Имя"
          />
          <base-form-input
            v-model="personAge"
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
            name-button="menu"
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
        <base-button
          class-name="button_save"
          name-button="save"
          @click="addPersonInfo"
        >
          Сохранить
        </base-button>
      </base-form>
      <person-info
        v-else
        :person-info="person"
      />
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
      personName: '',
      personAge: '',
      person: {
        name: null,
        age: null,
      },
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
    addPersonInfo() {
      this.person = { name: this.personName, age: this.personAge };
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
