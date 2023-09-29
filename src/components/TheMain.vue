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
            :is-disabled="isMaxChildren"
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
          <transition-group
            name="fade"
            tag="ul"
            class="form__list"
          >
            <li
              v-for="(item, index) in children"
              :key="item.id"
              class="form__list-item"
            >
              <base-form-input
                v-model="item.name"
                input-name="name"
                input-type="text"
                label-text="Имя"
              />
              <base-form-input
                v-model="item.age"
                input-name="age"
                input-type="number"
                label-text="Возраст"
              />
              <base-button
                class-name="button_delete"
                name-button="delete"
                @click="deleteInput(index)"
              >
                Удалить
              </base-button>
            </li>
          </transition-group>
        </base-form-fieldset>
        <transition name="fade">
          <base-button
            v-show="showButtonSave"
            class-name="button_save"
            name-button="save"
            @click="addPersonInfo"
          >
            Сохранить
          </base-button>
        </transition>
      </base-form>
      <person-info
        v-else
        :person-info="person"
        :children-info="children"
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

export default {
  components: {
    SvgIcon,
    PersonInfo,
    BaseButton,
    BaseFormFieldset,
    BaseForm,
    BaseFormInput,
  },
  props: {
    viewComponent: {
      type: Boolean,
      default: true,
    },
  },
  data() {
    return {
      personName: '',
      personAge: '',
      person: {
        name: null,
        age: null,
      },
      children: [],
    };
  },
  computed: {
    showButtonSave() {
      return this.children.length > 0;
    },

    isMaxChildren() {
      return this.children.length >= 5;
    },
  },

  methods: {
    addComponent() {
      if (!this.isMaxChildren) {
        const newItem = {
          id: Date.now(),
          name: null,
          age: null,
        };
        this.children.push(newItem);
      }
    },
    deleteInput(index) {
      this.children.splice(index, 1);
    },
    addPersonInfo() {
      this.person = {
        name: this.personName,
        age: this.personAge,
      };
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

.fade {
  &-enter-active, &-leave-active {
    transition: opacity 0.5s linear;
  }

  &-enter, &-leave-to {
    opacity: 0;
  }

}
</style>
