<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

</script>

<template>
  <header>
   <TheHeader />
  </header>
  <main>
   <RouterView />
  </main>
  <footer>
    <TheFooter />
  </footer>
</template>

<style scoped>

</style>
