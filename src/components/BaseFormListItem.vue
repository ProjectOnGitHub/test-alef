<template>
  <li class="form__list-item">
    <base-form-input
      v-model="childName"
      input-name="name"
      input-type="text"
      label-text="Имя"
      @input="updateParentValue"
    />
    <base-form-input
      v-model="childAge"
      input-name="age"
      input-type="number"
      label-text="Возраст"
      @input="updateParentValue"
    />
    <base-button
      class-name="button_delete"
      name-button="delete"
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

  props: {
    personInfo: {
      type: Object,
      default: () => {
      },
    },
  },

  data() {
    return {
      childName: '',
      childAge: null,
      tempObject: {},
    };
  },
  methods: {
    updateParentValue() {
      this.tempObject = { name: this.childName, age: this.childAge };
      this.$emit('input-change', this.tempObject);
    },
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
