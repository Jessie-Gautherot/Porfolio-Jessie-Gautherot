<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const goHome = () => {
  router.push('/');
};
</script>

<template>
 <section>
    <img src="@/assets/not found 2.jpg" alt="illustration error 404">
    <h1>Désolé, cette page n'existe pas</h1>
        <p>Revenez sur la page d'accueil !</p>
        <button @click="goHome">Page d'accueil</button>
</section>
  
</template>

<style scoped>



section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-bottom: 50px;
    box-sizing: border-box;
    background-color: #ffdb9e;
}



img {
    margin-top: 200px;
    width: 40%;
    height: 40%;
    border : 2px solid black;
    box-shadow: 0px 0px 10px black;
    box-sizing: border-box;
    align-items: center;
}

button { 
  padding: 0.8rem;
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

</style>
