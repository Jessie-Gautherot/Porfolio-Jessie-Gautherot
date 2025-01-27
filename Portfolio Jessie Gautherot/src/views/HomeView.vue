<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
</script>

<template>
  <main>
    <section id="about" class="section">
      <div class="about-text">
        <h1>A propos de moi</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint eveniet atque...</p>
      </div>
      <div class="about-picture">
        <img src="../assets/photo_de_profil.jpg" alt="my picture">
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

#about {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  
  
}

.about-text {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  width: 300px;
}

.about-picture {
  display: flex;
  width: 200px;
  height: auto;
  object-fit: cover;
  border-radius: 50%;
  box-sizing: border-box;
  border: 2px solid black;
  box-shadow: 10px 5px 5px black;
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
  min-height: 100vh;
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

