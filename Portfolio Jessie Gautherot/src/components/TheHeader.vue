<template>
  <section>
    <a href="#about"><img src="@/assets/photo_de_profil.jpg" alt="my picture"></a>
    <h1>Portfolio de Jessie Gautherot</h1>
    <nav>
      <ul>
        <li>
          <!--Attribut la classe "active" si l'utilisateur clique sur un de ces liens-->
          <a href="#about":class="{ active: activeLink === 'about' }">A propos</a>
        </li>
        <li>
          <a href="#works":class="{ active: activeLink === 'works' }">Réalisations</a>
        </li>
        <li>
          <a href="#contact":class="{ active: activeLink === 'contact' }">Contact</a>
        </li>
      </ul>
    </nav>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';
//variable réactive qui contient le lien actif
const activeLink = ref('');
// Mettre à jour "activeLink" en fonction du hash
const updateActiveLink = () => {
  const hash = window.location.hash.substring(1);
  if (hash) {
    activeLink.value = hash;
  } else {
    activeLink.value = 'about'; // Valeur par défaut si aucun hash
  }
};
// Ecoute de l'évènement "hashchange", appel de "updateActiveLink" pour la
// mise à jour de "activeLink"
onMounted(() => {
  updateActiveLink();
  window.addEventListener('hashchange', updateActiveLink);
});
</script>

<style scoped>
section { 
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  width: 100%;
  background-color: #324955;
}

img {
  width: 130px;
  height: 130px;
  object-fit: cover;
  border-radius: 50%;
  border: 2px solid #423849;
  box-shadow: 0px 0px 10px black;
  box-sizing: border-box;
  margin: 10px;
}

h1 {
  color: #ffdb9e;
  font-size: 2.5rem;
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
  color: #ffdb9e;
  font-size: 1.5rem;
}

a.active {
  text-decoration: underline;
}
</style>
