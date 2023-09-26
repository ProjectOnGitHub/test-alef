<template>
  <header class="header">
    <div class="header__container">
      <svg-icon
        icon-name="logo"
        icon-class="logo"
      />
      <nav class="header__navigation">
        <ul class="header__menu">
          <li class="header__menu-item">Форма</li>
          <li class="header__menu-item">Превью</li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
import imagesMap from '../utils/images';
import SvgIcon from './SvgIcon.vue';

export default {
  components: { SvgIcon },
  data() {
    return {
      images: imagesMap
    };
  }
};
</script>

<style lang="scss" scoped></style>
