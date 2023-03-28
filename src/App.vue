<script setup>
import SplashScreen from "./components/SplashScreen.vue";
import { defineAsyncComponent } from "vue";

const Home = defineAsyncComponent(() => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve(import("./components/Home.vue"));
    }, 2500);
  });
});
</script>

<template>
  <Suspense>
    <template #default>
      <Home></Home>
    </template>
    <template #fallback>
      <splash-screen></splash-screen>
    </template>
  </Suspense>
</template>

<style scoped>
</style>
