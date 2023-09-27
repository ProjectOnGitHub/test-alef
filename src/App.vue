<template>
  <div class="root">
    <the-header
      @clickToFormButton="viewForm"
      @clickToPreviewButton="viewPreview"
    />
    <the-main :view-component="isVisible" />
    <the-footer />
  </div>
</template>

<script>
import TheFooter from './components/TheFooter.vue';
import TheHeader from './components/TheHeader.vue';
import TheMain from './components/TheMain.vue';

export default {
  components: { TheHeader, TheMain, TheFooter },

  data() {
    return {
      isVisible: true,
    };
  },
  methods: {
    viewForm() {
      if (!this.isVisible) {
        this.isVisible = true;
      }
    },
    viewPreview() {
      if (this.isVisible) {
        this.isVisible = false;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.root {
  @include gridable();
  grid-template-columns: 1fr;
  justify-items: center;
  align-content: space-between;
  box-sizing: border-box;
  min-height: 100vh;
  grid-template-rows: auto 1fr auto;
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
  font-weight: normal;
  font-size: 14px;
  color: $colors-black;
  background-color: $colors-white;
  box-shadow: $box-shadow;
}
</style>
