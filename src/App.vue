<script setup>
import Navbar from "./components/navigation/Navbar.vue";
</script>

<template>
  <header>
    <Navbar />
  </header>

  <RouterView />
</template>

<style>
@import "@/assets/css/styles.css";
</style>
