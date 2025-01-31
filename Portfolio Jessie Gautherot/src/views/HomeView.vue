<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
import AboutMe from '@/components/AboutMe.vue';
import MyWorks from '@/components/MyWorks.vue';
</script>

<template>
  <main>
    <section id="about" class="section">
      <h1>A propos de moi</h1>
        <AboutMe></AboutMe>
   </section>

    <section id="works" class="section">
      <h1>Mes réalisations</h1>
        <MyWorks></MyWorks>
    </section>

    <section id="contact" class="section">
      <h1>Contactez-moi</h1>
      <ContactForm3></ContactForm3>
    </section>
  </main>
</template>

<style scoped>



main {
  background-color:#ffdb9e;
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


h1 {
  font-size: xx-large;
  color: #001c2f;
  text-decoration: underline #001c2f ;
  text-underline-offset: 9px;
}

h2 {
  font-size: large;
  align-items: center;
}
</style>

