<template>
  <div class="largeCategory">
    <h3 class="title h3">
      <slot name="title"> Заголовок </slot>
    </h3>
    <div class="categories">
      <div class="subTitle">
        <slot name="subTitle" class="text"> Заголовок </slot>
      </div>
    </div>
    <div class="imgWrapper">
      <slot name="img"
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
    overflow: hidden;
  }
  .title {
    z-index: 1;
  }
  .subTitle {
    margin-top: 10px;
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    gap: 10px;
  }
  .subTitle > a {
    margin-top: 10px;
  }

  @media screen and (max-width: 850px) {
    .img {
      position: absolute;
      width: 350px;
      height: 350px;
      top: -15px;
      right: unset;
      left: 50%;
      transform: translateX(-50%) translateY(40%);
    }
    .categories {
      width: 100%;
      z-index: 1;
    }
    .subTitle {
      display: inline-grid;
      grid-template-columns: repeat(2, 1fr);

      font-weight: 400;
      font-size: 12px;
      line-height: 16px;
    }
  }
  @media screen and (max-width: 450px) {
    .img {
      width: 190px;
      height: 190px;
      right: unset;
      left: 50%;
      transform: translateX(-50%) translateY(90%);
    }
    .subTitle {
      gap: 5px;
    }
    .largeCategory {
      padding: 15px;
    }
  }
</style>
