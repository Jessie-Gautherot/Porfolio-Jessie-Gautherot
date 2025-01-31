<script setup>
import { ref, onMounted } from 'vue';

const activeLink = ref('');

// Mettre à jour le lien actif selon le hash de l'URL
const updateActiveLink = () => {
  const hash = window.location.hash.substring(1);
  if (hash) {
    activeLink.value = hash;
  } else {
    activeLink.value = 'about'; // Valeur par défaut si aucun hash
  }
};

// Vérifier l'ancre à chaque changement de hash
onMounted(() => {
  updateActiveLink();
  window.addEventListener('hashchange', updateActiveLink);

});
</script>

<template>
  <header>
    <a href="#about"><img src="@/assets/photo_de_profil.jpg" alt="my picture"></a>
    <h1>Portfolio de Jessie Gautherot</h1>
    <nav>
      <ul>
        <li>
          <a 
            href="#about" 
            :class="{ active: activeLink === 'about' }"
          >A propos</a>
        </li>
        <li>
          <a 
            href="#works" 
            :class="{ active: activeLink === 'works' }"
          >Réalisations</a>
        </li>
        <li>
          <a 
            href="#contact" 
            :class="{ active: activeLink === 'contact' }"
          >Contact</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  width: 100%;
  background-color: #635654;
}

img {
  width: 130px;
  height: 130px;
  object-fit: cover;
  border-radius: 50%;
  border: 2px solid #30243a;
  box-shadow: 0px 0px 10px black;
  box-sizing: border-box;
  margin: 10px;
}

h1,
li {
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
  color: aliceblue;
  font-size: larger;
}

a.active {
  text-decoration: underline;
}
</style>
