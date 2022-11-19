<script setup>
import CategoriesCard from "./components/CategoriesCard.vue";

const categories = [
  { id: 1, image: "categories-1.jpg", title: "Mobile UI Kit", count: 731 },
  { id: 2, image: "categories-2.jpg", title: "Fonts ", count: 657 },
  { id: 3, image: "categories-3.jpg", title: "Icon Set ", count: 83.559 },
  { id: 4, image: "categories-4.jpg", title: "Website UI Kit ", count: 4.5 },
];
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-medium md:mb-0 md:text-lg">Top Categories</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <CategoriesCard
        v-for="(categorie, index) in categories"
        :key="index"
        :image="categorie.image"
        :title="categorie.title"
        :count="categorie.count"
      />
    </div>
  </div>
</template>
