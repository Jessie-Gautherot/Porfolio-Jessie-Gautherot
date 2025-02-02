<template>
  <div class="logo">
    <a href="https://www.facebook.com/jessie.gautherot/"target="_blank" rel="noopener noreferrer"><img src="@/assets/facebook(1).png" alt="logo facebook"></a>
    <a href="https://github.com/Jessie-Gautherot" target="_blank" rel="noopener noreferrer"><img src="@/assets/github.png" alt="logo github"></a>
    <a href="https://www.instagram.com/epicalys" target="_blank" rel="noopener noreferrer"><img src="@/assets/instagram(1).png" alt="logo instagram"></a>
  </div>
  <div>
    <small>
      <p>Dernière modification le <time datetime="2025-01-31">31 janvier 2025</time> </p>
    </small>
  </div>
</template>

<script setup>
</script>

<style scoped>
div {
  background-color:  #e47a51;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 20px;
}

.logo {
  display: flex;
  flex-direction: row;
}

img {
  width: 60px;
  height: 60px;
  padding: 10px;
  margin-bottom: 1px;
}
</style>