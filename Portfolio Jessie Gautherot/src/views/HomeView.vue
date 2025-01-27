<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
</script>

<template>
  <main>
    <section id="about" class="section">
      <div class="about-text">
        <h1>A propos de moi</h1>
        <p>Bonjour, je m'appelle Jessie Gautherot et je suis passionnée par le développement web.
Actuellement, je suis en formation de développeur web et web mobile au CEF. J'ai eu l'opportunité de travailler 
sur plusieurs projets, qui m'ont permis d'acquérir une solide base dans le développement d'interfaces utilisateur 
et de développer mes compétences techniques, notamment avec des frameworks modernes comme Vue.js.
Ce qui me plaît dans le développement web, c'est la possibilité de donner vie à des idées.
J'aime créer des interfaces intuitives et interactives qui répondent aux besoins des utilisateurs. 
Cela me permet de combiner ma créativité avec des compétences techniques, pour proposer des solutions efficaces et agréables.
Mon objectif est de continuer à évoluer, pour contribuer à des projets plus complexes,
tout en perfectionnant mes compétences techniques et créatives. </p>
      </div>
    </section>

    <section id="works" class="section">
      <h1>Mes réalisations</h1>
      <div>
        <h2>Mon CV en HTML et CSS</h2>
        <img src="../assets/image cv 2.png" alt="picture of my Curriculum Vitae">
      </div>
      <div>
        <h2>Mon cahier des charges</h2>
        <img src="../assets/picture-cahier-des-charges.png" alt="picture of specifications for a site">
      </div>
      <div>
        <h2>Dynamisme d'un espace commentaire en Javascript</h2>
        <img src="../assets/picture-javascript.png" alt="picture javascript project">
      </div>
    </section>

    <section id="contact" class="section">
      <h1>Contactez-moi</h1>
      <ContactForm3></ContactForm3>
    </section>
  </main>
</template>

<style scoped>

/*Eviter que le header ne cache les sections */

.section {
  padding-top: 120px;
}



/* Mise en forme de la page */
main {
  background-color: #F3D9B0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
}



.about-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 300px;
}


#works {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 30px;
  padding-bottom: 20px;
}

section {
  padding: 20px;
  
}

img {
  width: 200px;
  height: auto;
  border: 2px solid black;
}

img:hover {
  box-shadow: 10px 5px 5px black;
}

h1 {
  font-size: xx-large;
  color: #156062;
}

h2 {
  font-size: large;
}
</style>

