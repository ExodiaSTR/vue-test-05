<template>
  <div class="category">
    <h5 class="title h5">{{ category_data.title }}</h5>
    <div class="imgWrapper">
      <img
        :src="require('../assets/images/' + category_data.img)"
        alt="category-img"
        class="img"
      />
    </div>
  </div>
</template>

<script>
  export default {
    name: "TheCategory",
    props: {
      category_data: {
        type: Object,
        default: () => ({}),
      },
    },
  };
</script>

<style scoped>
  .category {
    cursor: pointer;
    position: relative;
    min-height: 125px;
    min-width: 99px;
    overflow: hidden;
  }
  .title {
    padding: 15px;
    height: 42px;
  }
  .imgWrapper {
    position: absolute;
    height: 115px;
    width: 100%;
    bottom: 0;
  }
  .img {
    position: absolute;
    max-width: 100%;
    max-height: 100%;
    right: 0;
    bottom: 0;
  }
  @media screen and (max-width: 450px) {
    .img {
      max-width: 80%;
      max-height: 80%;
    }
  }
</style>
