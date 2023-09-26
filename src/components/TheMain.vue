<template>
  <main class="main">
    <div class="main__container">
      <base-form />
    </div>
  </main>
</template>

<script>

import BaseForm from './BaseForm.vue';

export default {
  components: { BaseForm },

};
</script>

<style lang="scss" scoped>
.main {
  @include gridable();
  box-sizing: border-box;

  &__container {
    @include  flexible();
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }
}

</style>
