<script setup>

</script>

<template>
  <footer>
    <div class="logo">
      <a href="https://www.facebook.com/jessie.gautherot/"target="_blank" rel="noopener noreferrer"><img src="../assets/facebook(1).png" alt="logo facebook"></a>
      <a href="https://github.com/Jessie-Gautherot" target="_blank" rel="noopener noreferrer"><img src="../assets/github.png" alt="logo github"></a>
      <a href="https://www.instagram.com/epicalys" target="_blank" rel="noopener noreferrer"><img src="../assets/instagram(1).png" alt="logo instagram"></a>
    </div>
    <div>
      <small>
       <p>Dernière modification le <time datetime="2025-01-18">18 janvier 2025</time> </p>
      </small>
    </div>
  </footer>
</template>

<style scoped>

footer {
  background-color:  #156062;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: auto;
  width: 100%;
  box-sizing: border-box;
  /*margin: 0%;
  padding: 0%;
  border: 0%;*/
  margin: auto;
}

template {
  margin: auto;
}

.logo {
  display: flex;
  flex-direction: row;
}

img {
  width: 60px;
  height: 60px;
  padding: 10px;
  margin-bottom: 20px;
}

</style>