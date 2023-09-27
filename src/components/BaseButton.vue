<template>
  <button
    type="button"
    :class="className"
    :name="`button-${nameButton}`"
    class="button"
    @click="$emit('click')"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    typeButton: {
      type: String,
      default: '',
    },
    className: {
      type: String,
      default: '',
    },
    nameButton: {
      type: String,
      default: '',
    },
  },
};
</script>

<style scoped lang="scss">
.button {
  @include flexible();
  @include button();
  border-radius: 100px;
  font-size: 14px;
  line-height: 1.7;
  font-weight: 400;
  padding: 10px 20px;
  max-width: max-content;
  height: max-content;

  &_add {
    color: $colors-primary;
    border: 2px solid $colors-primary;
    background-color: $colors-white;
    gap: 4px;
  }

  &_save {
    color: $colors-white;
    background-color: $colors-primary;
  }

  &_delete {
    color: $colors-primary;
    background-color: $colors-white;
    padding: 0;
  }

  &_menu {
    color: $colors-gray;
    background-color: $colors-white;
    padding: 0;
  }
}
</style>
