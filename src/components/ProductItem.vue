<template>
  <div class="productItemWrapper">
    <span class="discount"> -10% </span>
    <div class="imgWrapper">
      <img
        :src="require('@/assets/images/' + items_data.img)"
        alt="img"
        class="img"
      />
    </div>
    <div class="itemInfos">
      <span class="title">
        <slot name="title">{{ items_data.title }}</slot>
      </span>
      <div class="price">
        <div class="discountPriceWrapper">
          <span class="discountPriceSpan">С учетом бонусов</span>
          <span class="discountPrice">
            <slot name="discountPrice"> {{ items_data.discountPrice }}</slot>
          </span>
        </div>
        <div class="regularPriceWrapper">
          <span class="regularPriceSpan">Обычная цена</span>
          <span class="regularPrice">
            <slot name="regularPrice">{{ items_data.regularPrice }}</slot>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "ProductItem",
    props: {
      items_data: {
        type: Object,
        default: () => ({}),
      },
    },
  };
</script>

<style scoped>
  .productItemWrapper {
    cursor: pointer;
    position: relative;
    background-color: var(--color-gray-background);
    padding: 12px 15px;
    border-radius: 5px;
  }
  .discount {
    display: none;
    position: absolute;
    top: 13px;
    right: 13px;
    padding: 4px 5px;
    border-radius: 4px;
    color: var(--color-white);
    background-color: var(--color-green);

    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 13px;
  }
  .imgWrapper {
    height: 210px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--color-gray-background);
  }
  .img {
    max-width: 100%;
    max-height: 100%;
    background-color: transparent;
  }
  .itemInfos {
    display: flex;
    flex-direction: column;
    height: 62px;
    width: 100%;
  }
  .title {
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    white-space: nowrap;
    overflow: hidden;
  }
  .price {
    margin-top: 5px;
    display: flex;
    flex-direction: row;
    color: var(--color-gray-dark);
  }
  .discountPriceWrapper {
    display: flex;
    flex-direction: column;
  }
  .regularPriceWrapper {
    margin-left: 16px;
    display: flex;
    flex-direction: column;
  }
  .regularPriceSpan,
  .discountPriceSpan {
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 100%;
  }
  .discountPrice {
    margin-top: 4px;
    font-weight: 500;
    font-size: 21px;
    line-height: 100%;
    color: var(--color-black);
  }
  .regularPrice {
    margin-top: 4px;
  }
  @media screen and (max-width: 850px) {
    .title {
      font-style: normal;
      font-weight: 400;
      font-size: 11px;
      white-space: nowrap;
      overflow: hidden;
    }
    .discountPriceSpan,
    .regularPriceSpan,
    .regularPrice {
      display: none;
    }
    .discountPrice {
      white-space: nowrap;
      font-weight: 500;
      font-size: 12px;
      line-height: 14px;
    }
  }
  @media screen and (max-width: 650px) {
    .title {
      width: 100%;
      white-space: unset;
    }
    .imgWrapper {
      height: 110px;
    }
    .img {
      max-width: 80%;
      max-height: 80%;
    }
  }
</style>
