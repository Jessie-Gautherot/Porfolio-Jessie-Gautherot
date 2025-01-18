<script setup>

</script>

<template>
  <header>
    <img src="../assets/photo_de_profil.jpg" alt="my picture">
    <h1>Portfolio de Jessie Gautherot</h1>
    <nav>
      <ul>
        <li><a href="#about">A propos</a></li>
        <li><a href="#works">Réalisations</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>

header {
  display: flex;
  justify-content:space-between;
  align-items: center;
  position: fixed;
  top: 0;
  width: 100%;
  background-color: rgb(44, 44, 38);
  box-sizing: border-box;
  margin: 0%;
  padding: 0%;
  border: 0%;
}

img {
  width: 130px;
  height: 130px;
  object-fit: cover;
  border-radius: 50%;
  border : 2px solid black;
  box-shadow: 0px 0px 10px black;
  box-sizing: border-box;
  margin : 10px
}

h1, li {
  color: antiquewhite;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

ul {
  display: flex;
  flex-direction: row;
  padding-right: 10px;
}

li {
  padding: 15px;
  list-style-type: none;
}

a {
  text-decoration: none;
  font-size: larger;
}

</style>