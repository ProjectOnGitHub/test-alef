<template>
  <form class="form">
    <slot></slot>
  </form>
</template>

<style lang="scss" scoped>

.form {
  @include flexible();
  flex-direction: column;
  max-width: 616px;
  box-sizing: border-box;
  gap: 33px;
}

</style>
