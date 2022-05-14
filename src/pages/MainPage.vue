<template>
  <div class="wrapper">
    <div class="section">
      <LargeCategory class="largeCategory">
        <template #title> Телефоны </template>
        <template #subTitle>
          <div class="subTitle">
            <a href="#">Все телефоны</a>
            <a href="#">IPhone</a>
            <a href="#">Samsung</a>
            <a href="#">Xiaomi</a>
            <a href="#">Honor</a>
            <a href="#">OPPO</a>
            <a href="#">Huawei</a>
            <a href="#">Для телефонов</a>
          </div>
        </template>
      </LargeCategory>
      <div class="categories">
        <TheCategory
          v-for="category in categoryData"
          :key="category.id"
          :category_data="category"
          class="category"
        />
      </div>
    </div>
    <div class="section secondSection">
      <h2 class="h2">День знаний</h2>

      <div class="sectionRow">
        <div class="eventCategories">
          <TheCategory
            v-for="category in eventCategoryData"
            :key="category.id"
            :category_data="category"
            class="eventCategory"
          />
        </div>
        <LargeCategory class="secondaryLargeCategory">
          <template #title> Бытовая техника </template>
          <template #subTitle>
            <div class="subTitle">
              <a href="#">Техника для дома</a>
              <a href="#">Крупная бытовая техника</a>
              <a href="#">Техника для кухни</a>
              <a href="#">Встраиваемая техника</a>
              <a href="#">Техника для дома</a>
              <a href="#">Приготовление кофе и чая</a>
              <a href="#">Фильтры для воды</a>
            </div>
          </template>
          <template #img>
            <img
              :src="require('@/assets/images/washer.png')"
              alt="IPhone"
              class="img"
            />
          </template>
        </LargeCategory>
      </div>
    </div>
  </div>
</template>

<script>
  import TheCategory from "@/components/TheCategory.vue";
  import LargeCategory from "@/components/LargeCategory.vue";

  export default {
    components: {
      TheCategory,
      LargeCategory,
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
    }),
  };
</script>

<style scoped>
  .wrapper {
    max-width: 1500px;
    margin: 0 auto;
  }
  .section {
    display: flex;
  }
  .secondSection {
    margin-top: 44px;
    flex-direction: column;
  }
  .sectionRow {
    margin-top: 29px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    border-radius: 5px;
    border: 0.5px solid var(--color-border);
    overflow: hidden;
  }
  .categories {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
    max-width: 1200px;
  }
  .eventCategories {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    max-width: 1500px;
    grid-gap: 0px;
    border-radius: 0px;
  }

  .category {
    border-radius: 5px;
    margin-top: 0px;
    background-color: var(--color-gray);
  }
  .eventCategory {
    border-radius: 0px;
    background-color: var(--color-white);
    border: 0.5px solid var(--color-border);
    overflow: hidden;
  }
  .largeCategory {
    margin-right: 10px;
  }
  .secondaryLargeCategory {
    background-color: var(--color-white);
    border-radius: 0px;
    width: 100%;
    margin-right: 0px;
  }
  .subTitle {
    display: flex;
    flex-direction: column;
  }
  .subTitle > a {
    margin-top: 10px;
  }
  .img {
    position: absolute;
    max-width: 100%;
    max-height: 100%;
    bottom: -50px;
    right: -10px;
    transform: scale(-1, 1);
  }
</style>
