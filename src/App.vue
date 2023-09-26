<template>
  <div class="root">
    <the-header />
    <the-main />
    <the-footer />
  </div>
</template>

<script>
import TheFooter from './components/TheFooter.vue';
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';

export default {
  components: { TheHeader, TheMain, TheFooter }
};
</script>

<style lang="scss" scoped>
.root {
  @include gridable();
  grid-template-columns: 1fr;
  justify-items: center;
  align-content: space-between;
  box-sizing: border-box;
  height: 100%;
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
  font-weight: normal;
  font-size: 14px;
  background-color: $colors-white;
  box-shadow: $box-shadow;
}
</style>
