<template>
  <button
    type="button"
    :class="isActive ? `${className} active` : className"
    :disabled="isDisabled"
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
    className: {
      type: String,
      default: '',
    },
    nameButton: {
      type: String,
      default: '',
    },
    isDisabled: {
      type: Boolean,
      default: false,
    },
    isActive: {
      type: Boolean,
    },
  },
};
</script>

<style lang="scss">
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

  &:disabled,
  &:disabled:hover {
    cursor: default;
    color: $colors-gray;
    background-color: $colors-white;
    border: 2px solid $colors-gray-s;

    .plus {
      fill: $colors-gray;
    }
  }

  &_add {
    color: $colors-primary;
    border: 2px solid $colors-primary;
    background-color: $colors-white;
    gap: 4px;

    &:hover {
      background-color: $colors-primary;
      color: $colors-white;

      .plus {
        fill: $colors-white;
      }
    }

  }

  &_save {
    color: $colors-white;
    background-color: $colors-primary;
    border: solid 2px $colors-white;

    &:hover {
      color: $colors-primary;
      background-color: $colors-white;
      border: 2px solid $colors-primary;
    }
  }

  &_delete {
    color: $colors-primary;
    background-color: $colors-white;
    padding: 0;

    &:hover {
      opacity: 0.65;
    }
  }

  &_menu {
    color: $colors-gray;
    background-color: $colors-white;
    padding: 0;

    &:hover {
      opacity: 0.65;
    }

    &.active {
      color: $colors-primary;
    }
  }
}
</style>
