<script setup>
import ItemsCard from "./components/ItemsCard.vue";

const items = [
  {
    id: 1,
    image: "/src/assets/img/items-1.jpg",
    title: "Mobile UI Kit",
    subTitle: "Mobile UI Kit",
  },
  {
    id: 2,
    image: "/src/assets/img/items-2.jpg",
    title: "Online Doctor Consultation",
    subTitle: "Website UI Kit",
  },
  {
    id: 3,
    image: "/src/assets/img/items-3.jpg",
    title: "Banking Crypto",
    subTitle: "Mobile UI Kit",
  },
];
</script>

<template>
  <div class="container px-4 mx-auto my-16 md:px-12">
    <h2 class="mb-4 text-xl font-semibold md:mb-0 md:text-lg">New Items</h2>
    <div class="flex flex-wrap -mx-1 lg:-mx-4">
      <ItemsCard
        v-for="(item, index) in items"
        :key="index"
        :image="item.image"
        :title="item.title"
        :subTitle="item.subTitle"
      />
    </div>
  </div>
</template>
