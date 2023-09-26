<template>
  <form class="form">
    <slot></slot>
  </form>
</template>

<style lang="scss" scoped>

.form {
  @include flexible();
  @include defaultContainer;
  gap: 33px;
}

</style>
