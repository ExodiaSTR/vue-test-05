<template>
  <div class="largeCategory">
    <h3 class="title h3">
      <slot name="title"> Заголовок </slot>
    </h3>
    <div class="categories">
      <slot name="subTitle" class="text"> Заголовок </slot>
    </div>
    <div class="imgWrapper">
      <slot name="img" class="img"
        ><img
          :src="require('@/assets/images/iphone.png')"
          alt="IPhone"
          class="img"
      /></slot>
    </div>
  </div>
</template>

<script>
  export default {};
</script>

<style scoped>
  .largeCategory {
    display: flex;
    flex-direction: column;
    position: relative;
    padding: 21px 25px;
    min-width: 389px;
    max-width: 520px;
    background-color: var(--color-tuquoise-light);
    border-radius: 5px;
    overflow: hidden;
  }
  .categories {
    width: 150px;
    z-index: 1;
  }
  .img {
    position: absolute;
    width: 450px;
    height: 450px;
    top: -15px;
    right: -115px;
  }
  .title {
    z-index: 1;
  }
</style>
