<template>
  <div class="person">
    <div class="person__info">
      <h2 class="person__info-title">
        Персональные данные
      </h2>
      <p class="person__info-description">
        Имя, 30 лет
      </p>
    </div>
    <div class="person__info">
      <h2 class="person__info-title">
        Дети
      </h2>
      <ul class="person__list">
        <li class="person__list-item">
          Имя, 10 лет
        </li>
        <li class="person__list-item">
          Имя, 10 лет
        </li>
      </ul>
    </div>
  </div>
</template>

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
