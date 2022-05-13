<template>
  <div class="category">
    <h3 class="title h3">
      <slot name="title"> Заголовок </slot>
    </h3>
    <div class="categories">
      <slot name="subTitle"> Заголовок </slot>
    </div>
    <img src="@/assets/images/iphone.png" alt="IPhone" class="img" />
  </div>
</template>

<script>
  export default {};
</script>

<style scoped>
  .category {
    position: relative;
    padding: 21px 25px;
    min-width: 389px;
    max-width: 489px;
    background-color: var(--color-tuquoise-light);
    border-radius: 5px;
    overflow: hidden;
  }
  .categories {
    width: 150px;
  }
  .img {
    position: absolute;
    top: -15px;
    right: -150px;
  }
</style>
