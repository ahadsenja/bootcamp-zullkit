<script setup>
import TheLogo from "./components/Logo.vue";
import AuthButton from "./components/AuthButton.vue";
import NavigationLink from "./components/NavigationLink.vue";
</script>

<template>
  <nav
    class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800"
  >
    <div
      class="container flex flex-wrap items-center justify-between mx-auto my-2"
    >
      <TheLogo />
      <AuthButton />
      <NavigationLink />
    </div>
  </nav>
</template>
