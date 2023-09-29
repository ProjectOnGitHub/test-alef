<template>
  <footer class="footer">
    <p class="footer__text">
      All rights reserved
    </p>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.footer {
  @include flexible();
  justify-content: center;
  box-sizing: border-box;
  padding: 30px 92px;
  background-color: $colors-gray-m;
  box-shadow: $box-shadow;

  &__text {
    text-transform: lowercase;
    font-size: 13px;
  }
}
</style>
