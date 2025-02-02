<template>
  <section>
    <img src="@/assets/not found 2.jpg" alt="illustration error 404">
    <h1>Désolée, cette page n'existe pas</h1>
    <p> Revenez sur la page d'accueil, en cliquant sur le bouton !</p>
    <button @click="goHome">Page d'accueil</button>
  </section>
</template>

<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

// Redirection vers la page d'accueil
const goHome = () => {
  router.push('/');
};
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-bottom: 50px;
  background-color: #ffdb9e;
}

img {
  margin-top: 200px;
  width: 40%;
  height: 40%;
  border : 2px solid black;
  box-shadow: 0px 0px 10px #35434b;
}

button { 
  padding: 1rem;
  background-color: #35434b;
  color: #ffdb9e;
  border: 1px solid #001c2f;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer
}

button:hover {
  background-color: #e47a51; 
}

p {
  font-size: 1.3rem;
}
</style>
