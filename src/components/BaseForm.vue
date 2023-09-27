<template>
  <form class="form">
    <slot></slot>
  </form>
</template>

<style lang="scss">

.form {
  @include flexible();
  @include defaultContainer;
  gap: 33px;

  &__list {
    @include flexible();
    @include unmarkedList;
  }
}

</style>
