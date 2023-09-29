<template>
  <header class="header">
    <div class="header__container">
      <svg-icon
        icon-name="logo"
        icon-class="logo"
      />
      <nav class="header__navigation">
        <ul class="header__menu">
          <li class="header__menu-item">
            <base-button
              :is-active="isActive"
              class-name="button_menu"
              name-button="menu"
              @click="$emit('clickToFormButton')"
            >
              Форма
            </base-button>
          </li>
          <li class="header__menu-item">
            <base-button
              :is-active="!isActive"
              class-name="button_menu"
              name-button="menu"
              @click="$emit('clickToPreviewButton')"
            >
              Превью
            </base-button>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
import imagesMap from '../utils/images';
import SvgIcon from './SvgIcon.vue';
import BaseButton from './BaseButton.vue';

export default {
  components: {
    BaseButton,
    SvgIcon,
  },
  props: {
    isActive: {
      type: Boolean,
    },
  },
  data() {
    return {
      images: imagesMap,
    };
  },
};

</script>

<style lang="scss" scoped>
.header {
  @include flexible();
  justify-content: center;
  box-sizing: border-box;
  box-shadow: $box-shadow;

  &__container {
    @include gridable();
    grid-template-columns: max-content 1fr;
    justify-content: space-between;
    padding: 22px 92px;
    align-items: center;
    gap: 24px;
    max-width: 1366px;

    @media screen and (max-width: $desktop) {
      padding-left: 20px;
      padding-right: 20px;
    }
  }

  &__navigation {
    @include flexible();
    justify-content: center;
  }

  &__menu {
    @include unmarkedList;
    @include flexible(max-content);
    gap: 24px;
    line-height: 1.71;
    color: $colors-gray;
  }
}
</style>
