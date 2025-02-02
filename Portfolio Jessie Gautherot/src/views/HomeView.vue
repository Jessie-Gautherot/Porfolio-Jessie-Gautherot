<template>
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
      <ContactForm></ContactForm>
  </section>
</template>

<script setup>
import ContactForm from '@/components/ContactForm.vue';
import AboutMe from '@/components/AboutMe.vue';
import MyWorks from '@/components/MyWorks.vue';
</script>

<style scoped>
section {
  background-color:#ffdb9e;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 140px;
  padding-bottom: 30px;
}

h1 {
  font-size: 2rem;
  color: #001c2f;
  text-decoration: underline #001c2f ;
  text-underline-offset: 9px;
}

h2 {
  font-size: 1.5rem;
  align-items: center;
}
</style>

