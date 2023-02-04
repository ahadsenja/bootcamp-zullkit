<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
import ItemsCard from "./components/ItemsCard.vue";

const products = ref([]);

async function getProductsData() {
  try {
    const response = await axios.get(
      "http://zullkit-backend.buildwithangga.id/api/products"
    );
    products.value = response.data.data.data;
  } catch (error) {
    console.log(error);
  }
}

onMounted(() => {
  getProductsData();
});
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-semibold md:mb-0 md:text-lg">New Items</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <ItemsCard
        v-for="(product, index) in products"
        :key="index"
        :id="product.id"
        :image="product.thumbnails"
        :title="product.name"
        :subTitle="product.subtitle"
      />
    </div>
  </div>
</template>
