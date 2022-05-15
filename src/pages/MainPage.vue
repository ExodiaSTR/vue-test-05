<template>
  <div class="wrapper">
    <div class="firstSection">
      <LargeCategory class="largeCategory">
        <template #title> Телефоны </template>
        <template #subTitle>
          <a href="#">Все телефоны</a>
          <a href="#">IPhone</a>
          <a href="#">Samsung</a>
          <a href="#">Xiaomi</a>
          <a href="#">Honor</a>
          <a href="#">OPPO</a>
          <a href="#">Huawei</a>
          <a href="#">Для телефонов</a>
        </template>
      </LargeCategory>
      <TheCategory
        v-for="category in categoryData"
        :key="category.id"
        :category_data="category"
        class="category"
      />
    </div>
    <div class="eventSectionWrapper">
      <h2 class="h2">День знаний</h2>
      <div class="secondSection">
        <TheCategory
          v-for="category in eventCategoryData"
          :key="category.id"
          :category_data="category"
          class="eventCategory"
        />
        <LargeCategory class="secondaryLargeCategory">
          <template #title> Бытовая техника </template>
          <template #subTitle>
            <a href="#">Техника для дома</a>
            <a href="#">Крупная бытовая техника</a>
            <a href="#">Техника для кухни</a>
            <a href="#">Встраиваемая техника</a>
            <a href="#">Техника для дома</a>
            <a href="#">Приготовление кофе и чая</a>
            <a href="#">Фильтры для воды</a>
          </template>
          <template #img>
            <img
              :src="require('@/assets/images/washer.png')"
              alt="IPhone"
              class="secondaryLargeCategoryImg"
            />
          </template>
        </LargeCategory>
      </div>
    </div>

    <div class="gridWrapper">
      <div class="itemsFirstbox">
        <LargeProductItem class="largeProductItem" />
        <ProductItem
          class="productItem"
          v-for="item in productItemsData"
          :key="item.id"
          :items_data="item"
        />
      </div>
      <div class="itemsFirstbox">
        <ProductItem
          class="productItem"
          v-for="item in productItemsData"
          :key="item.id"
          :items_data="item"
        />
        <LargeProductItem class="largeProductItem" />
      </div>
    </div>
  </div>
</template>

<script>
  import TheCategory from "@/components/TheCategory.vue";
  import LargeCategory from "@/components/LargeCategory.vue";
  import ProductItem from "@/components/ProductItem.vue";
  import LargeProductItem from "@/components/LargeProductItem.vue";

  export default {
    components: {
      TheCategory,
      LargeCategory,
      ProductItem,
      LargeProductItem,
    },
    data: () => ({
      categoryData: [
        {
          title: "Компьютерная Техника",
          id: "1",
          img: "notebook.png",
        },
        {
          title: "Офисная Техника",
          id: "2",
          img: "printer.png",
        },
        {
          title: "Компьютерная Техника",
          id: "3",
          img: "notebook.png",
        },
        {
          title: "Офисная Техника",
          id: "4",
          img: "printer.png",
        },
        {
          title: "Телевизоры, аудио, видео",
          id: "5",
          img: "TV.png",
        },
        {
          title: "Климатическая техника",
          id: "6",
          img: "conditioner.png",
        },
        {
          title: "Бытовая Техника",
          id: "7",
          img: "freeze.png",
        },
        {
          title: "Развлечения и игры",
          id: "8",
          img: "PS5.png",
        },
      ],
      eventCategoryData: [
        {
          title: "Рюкзаки и канцелярия",
          id: "21",
          img: "backpack.png",
        },
        {
          title: "Форма и обувь",
          id: "22",
          img: "form.png",
        },
        {
          title: "Компьютеры и гаджеты",
          id: "23",
          img: "notebook.png",
        },
        {
          title: "Комната школьника",
          id: "24",
          img: "chair.png",
        },
        {
          title: "Игрушки и игры",
          id: "25",
          img: "toys.png",
        },
        {
          title: "Завтраки и перекусы",
          id: "26",
          img: "food.png",
        },
        {
          title: "Аптечка и оптика",
          id: "27",
          img: "medications.png",
        },
        {
          title: "Рюкзаки и концелярия",
          id: "28",
          img: "backpack.png",
        },
      ],
      productItemsData: [
        {
          title: "Смартфон Apple iPhone 11 12...",
          regularPrice: "55 850 ₽",
          discountPrice: "54 490 ₽",
          img: "clock.png",
          id: "1",
        },
        {
          title: "Смартфон Apple iPhone 11 12...",
          regularPrice: "55 850 ₽",
          discountPrice: "54 490 ₽",
          img: "TVitem.png",
          id: "2",
        },
        {
          title: "Смартфон Apple iPhone 11 12...",
          regularPrice: "55 850 ₽",
          discountPrice: "54 490 ₽",
          img: "fitClock.png",
          id: "3",
        },
        {
          title: "Смартфон Apple iPhone 11 12...",
          regularPrice: "55 850 ₽",
          discountPrice: "54 490 ₽",
          img: "clock.png",
          id: "4",
        },
        {
          title: "Смартфон Apple iPhone 11 12...",
          regularPrice: "55 850 ₽",
          discountPrice: "54 490 ₽",
          img: "fitClock.png",
          id: "6",
        },
      ],
    }),
  };
</script>

<style scoped>
  .wrapper {
    max-width: 1500px;
    margin: 0 auto;
    height: 100%;
  }
  .firstSection {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: repeat(2, 1fr);
    gap: 10px;
  }
  .largeCategory {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 3;
  }
  .section {
    display: flex;
  }
  .eventSectionWrapper {
    margin-top: 44px;
    width: 100%;
  }
  .secondSection {
    width: 100%;
    margin-top: 29px;
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-auto-rows: 2;
    grid-gap: 2px;
    border: 1px solid var(--color-border);
    background-color: var(--color-border);
  }

  .secondaryLargeCategory {
    background-color: var(--color-white);
    border-radius: 0px;
    grid-column-start: 5;
    grid-column-end: 7;
    grid-row-start: 1;
    grid-row-end: 3;
  }

  .categories {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
    max-width: 1200px;
  }
  .category {
    border-radius: 5px;
    margin-top: 0px;
    background-color: var(--color-gray);
  }
  .eventCategory {
    border-radius: 0px;
    background-color: var(--color-white);
  }

  .secondaryLargeCategoryImg {
    position: absolute;
    max-width: 100%;
    max-height: 100%;
    bottom: -50px;
    right: -10px;
    transform: scale(-1, 1);
  }
  .gridWrapper {
    margin-top: 30px;
    display: flex;
    min-height: 840px;
    gap: 10px;
  }

  .itemsFirstbox {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    grid-gap: 10px;
  }

  .largeProductItem {
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 4;
  }
  .largeProductItem:last-child {
    grid-column-start: 2;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 3;
  }
</style>

<style scoped>
  @media screen and (max-width: 1510px) {
    .gridWrapper {
      margin-top: 30px;
      display: flex;

      flex-direction: column;
      min-height: 840px;
      gap: 10px;
    }
  }
  @media screen and (max-width: 1350px) {
    .firstSection {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(3, 1fr);
      gap: 10px;
    }
    .secondSection {
      margin-top: 29px;
      display: inline-grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: repeat(3, 1fr);
    }
    .secondaryLargeCategory {
      grid-column-start: 2;
      grid-column-end: 4;
      grid-row-start: 1;
      grid-row-end: 3;
    }
    .itemsFirstbox:last-child {
      display: none;
    }
    .gridWrapper {
      min-height: unset;
    }
  }
  @media screen and (max-width: 850px) {
    .firstSection,
    .secondSection,
    .itemsFirstbox {
      gap: 3px;
    }
    .largeProductItem {
      grid-column-start: 1;
      grid-column-end: 3;
      grid-row-start: 1;
      grid-row-end: 3;
    }
    .secondaryLargeCategoryImg {
      max-width: 100%;
      max-height: 100%;
      bottom: -70px;
      right: unset;
      left: 50%;
      transform: translateX(-50%) scale(-1, 1);
      width: 150px;
    }
  }
</style>
