<template>
  <div class="largeProductWrapper">
    <span class="discount"> -10% </span>
    <div class="imgWrapper">
      <img src="@/assets/images/iphoneItem.png" alt="img" class="img" />
    </div>
    <div class="itemInfos">
      <span class="title">
        <slot name="title"
          >{{ items_data.title }}Ультрабук Apple MacBook Air (2020 года)
          (MVH22RU/A) серый Ультрабук Apple
        </slot>
      </span>
      <div class="price">
        <div class="discountPriceWrapper">
          <span class="discountPriceSpan">С учетом бонусов</span>
          <span class="discountPrice">
            <slot name="discountPrice">
              {{ items_data.discountPrice }}54 490 ₽</slot
            >
          </span>
        </div>
        <div class="regularPriceWrapper">
          <span class="regularPriceSpan">Обычная цена</span>
          <span class="regularPrice">
            <slot name="regularPrice"
              >{{ items_data.regularPrice }} 55 850 ₽</slot
            >
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "LargeProductItem",
    props: {
      items_data: {
        type: Object,
        default: () => ({}),
      },
    },
  };
</script>

<style scoped>
  .largeProductWrapper {
    cursor: pointer;
    position: relative;
    background-color: var(--color-gray-background);
    padding: 12px 15px;
    border-radius: 5px;
    display: flex;
    flex-direction: column;
    justify-content: center;
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
    height: 450px;
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
    line-height: 140%;
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
    font-size: 14px;
    line-height: 100%;
  }
  .discountPrice {
    margin-top: 4px;
    font-weight: 500;
    font-size: 37px;
    line-height: 100%;
    color: var(--color-black);
  }
  .regularPrice {
    margin-top: 4px;
    font-weight: 500;
    font-size: 25px;
    line-height: 100%;
  }
  @media screen and (max-width: 850px) {
    .title {
      font-style: normal;
      font-weight: 400;
      font-size: 11px;
      white-space: nowrap;
    }
    .discountPriceSpan,
    .regularPriceSpan,
    .regularPrice {
      display: none;
    }
    .discountPrice {
      font-weight: 500;
      font-size: 12px;
      line-height: 14px;
    }
  }
  @media screen and (max-width: 650px) {
    .imgWrapper {
      height: 300px;
    }
    .title {
      white-space: unset;
    }
  }
</style>
