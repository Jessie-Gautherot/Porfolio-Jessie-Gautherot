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

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
</script>

<style>
</style>
