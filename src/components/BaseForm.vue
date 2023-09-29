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
    flex-direction: column;
    gap: 10px;

    &-item {
      @include flexible();
      gap: 10px 18px;
      align-items: center;
      flex-grow: 1;
      justify-content: flex-end;

      @media screen and (max-width: $mobile) {
        flex-wrap: wrap;
      }
    }
  }

}

</style>
