<script setup>
import { RouterLink, RouterView } from 'vue-router'
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

</script>

<template>
   <TheHeader />
  <main>
   <RouterView />
  </main>
    <TheFooter />
</template>

<style scoped>

template {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  margin: auto;
  height: 100%;
}

</style>
