<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
import AboutMe from '@/components/AboutMe.vue';
</script>

<template>
  <main>
    <section id="about" class="section"></section>
    <AboutMe></AboutMe>

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



main {
  background-color: #F3D9B0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

section {
  padding-top: 140px;
  padding-bottom: 40px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}


#works div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-bottom: 50px;
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

