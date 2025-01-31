<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
import AboutMe from '@/components/AboutMe.vue';
import MyWorks from '@/components/MyWorks.vue';
</script>

<template>
  <main>
    <section id="about" class="section">
    <AboutMe></AboutMe>
  </section>

    <section id="works" class="section">
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
  background-color: #e7c9f3;
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
  color: #464155;
}

h2 {
  font-size: large;
  align-items: center;
}
</style>

