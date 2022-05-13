<template>
  <div class="categories">
    <TheCategory
      v-for="category in categoryData"
      :key="category.id"
      :category_data="category"
    />
  </div>
</template>

<script>
  import TheCategory from "@/components/TheCategory.vue";
  export default {
    components: {
      TheCategory,
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
  .categories {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
    max-width: 1200px;
  }
</style>
