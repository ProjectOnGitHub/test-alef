<template>
  <svg
    :class="iconClass"
    aria-hidden="true"
  >
    <use :xlink:href="`#${iconName}`" />
  </svg>
</template>

<script>
export default {
  props: {
    iconName: {
      type: String,
      required: true,
    },
    iconClass: {
      type: String,
      default: '',
    },
  },
};
</script>

<style lang="scss" scoped>
.logo {
  width: 93px;
  height: 29px;
}

.plus {
  width: 24px;
  height: 24px;
}
</style>
