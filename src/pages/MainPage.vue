<template>
  <div class="wrapper">
    <div class="section">
      <LargeCategory class="largCategory">
        <template #title> Телефоны </template>
        <template #subTitle>
          <div class="subTitle">
            <a href="">Все телефоны</a>
            <a href="">IPhone</a>
            <a href="">Samsung</a>
            <a href="">Xiaomi</a>
            <a href="">Honor</a>
            <a href="">OPPO</a>
            <a href="">Huawei</a>
            <a href="">Для телефонов</a>
          </div>
        </template>
      </LargeCategory>
      <div class="categories">
        <TheCategory
          v-for="category in categoryData"
          :key="category.id"
          :category_data="category"
        />
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
  .categories {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
    max-width: 1200px;
  }
  .largCategory {
    margin-right: 10px;
  }
  .subTitle {
    display: flex;
    flex-direction: column;
  }
  .subTitle > a {
    margin-top: 10px;
  }
</style>
