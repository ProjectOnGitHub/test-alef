<template>
  <div
    v-if="personInfo.name"
    class="person"
  >
    <div class="person__info">
      <h2 class="person__info-title">
        Персональные данные
      </h2>
      <p class="person__info-description">
        {{ personInfo.name }}, {{ personInfo.age }} лет
      </p>
    </div>
    <div class="person__info">
      <h2 class="person__info-title">
        Дети
      </h2>
      <ul class="person__list">
        <li
          v-for="(child, index) in childrenInfo"
          :key="index"
          class="person__list-item"
        >
          {{ child.name }}, {{ child.age }} лет
        </li>
      </ul>
    </div>
  </div>
  <div
    v-else
    class="person"
  >
    <div class="person__info">
      <h2 class="person__info-title">
        Персональные данные не внесены
      </h2>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    personInfo: {
      type: Object,
      default: () => {
      },
    },
    childrenInfo: {
      type: Object,
      default: () => {
      },
    },
  },
};
</script>

<style scoped lang="scss">
.person {
  @include flexible();
  @include defaultContainer;
  gap: 60px;

  &__info {
    @include flexible();
    flex-direction: column;
    gap: 10px;

    &-title {
      @include defaultTitle;
    }
  }

  &__info-description, &__list {
    margin: 0;
    font-size: 16px;
    font-weight: 700;
    line-height: 1.5;
  }

  &__list {
    @include unmarkedList;
    @include flexible();
    flex-direction: column;
    gap: 20px;

    &-item {
      padding: 10px 20px;
      background-color: $colors-gray-l;
      border-radius: 5px;
      max-width: max-content;
      width: 100%;
    }
  }
}
</style>
