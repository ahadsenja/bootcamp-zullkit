<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
import CategoriesCard from "@/components/section/components/CategoriesCard.vue";

let categories = ref([]);

async function getCategoriesData() {
  try {
    const response = await axios.get(
      "http://zullkit-backend.buildwithangga.id/api/categories?show_product=1"
    );
    console.log(response.data.data.data);
    categories.value = response.data.data.data;
  } catch (error) {
    console.log(error);
  }
}

onMounted(() => {
  getCategoriesData();
});
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-semibold md:mb-0 md:text-lg">
      All Categories
    </h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <CategoriesCard
        v-for="(category, index) in categories"
        :key="index"
        :image="category.thumbnails"
        :title="category.name"
        :count="category.products_count"
      />
    </div>
  </div>
</template>
