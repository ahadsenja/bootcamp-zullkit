<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";

const defaultImage = ref([]);
const galleries = ref([]);

async function getGalleriesData() {
  try {
    const response = await axios.get(
      "http://zullkit-backend.buildwithangga.id/api/products"
    );
    galleries.value = response.data.data.data;
    defaultImage.value = response.data.data.data[2].thumbnails;
  } catch (error) {
    console.log(error);
  }
}

function handleImage(image) {
  defaultImage.value = image;
}

onMounted(() => {
  getGalleriesData();
});
</script>

<template>
  <section id="gallery">
    <img :src="defaultImage" alt="" class="w-full mt-6 rounded-2xl" />
    <div class="grid grid-cols-4 gap-4 mt-4">
      <template v-for="(gallery, index) in galleries" :key="index">
        <div
          @click="handleImage(gallery.thumbnails)"
          class="overflow-hidden cursor-pointer rounded-2xl"
          :class="{
            'ring-2 ring-indigo-500': defaultImage == gallery.thumbnails,
          }"
        >
          <img :src="gallery.thumbnails" class="w-full" alt="" />
        </div>
      </template>
    </div>
  </section>
</template>
