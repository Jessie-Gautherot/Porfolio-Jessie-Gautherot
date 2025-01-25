<script setup>
import ContactForm3 from '@/components/ContactForm3.vue';
  


</script>

<template>
  <main>
    <section id="about">
        <div class="about-text">
         <h1>A propos de moi</h1>
         <p>kjlkjlkjkljlkjkljkljklj
       Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint eveniet atque, dolorum mollitia consequuntur corporis ipsa ea porro, molestias ex magni, reiciendis quaerat laboriosam delectus labore. Voluptatum quia velit quaerat.</p>
      </div>
      <div class="about-picture">
        <img src="../assets/photo_de_profil.jpg" alt="my picture">
      </div>
    </section>
    <section id="works">
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
    <section id="contact">
      <h1>Contactez-moi</h1>
      <ContactForm3></ContactForm3>
      
        
        
        
    </section>
  </main>
</template>

<style scoped>

h1 {
  font-size: xx-large;
  color: #156062;
}

h2 {
  font-size:large }

main {
  padding-top: 140px;
  background-color:#F3D9B0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  align-items: center;
  right: O;
  left: 0;
  width: 100%;
}

* {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#about{
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  justify-items: center;
  gap: 60px;
  padding-top: 150px;
  padding-bottom: 70px;
  
}

.about-text {
  display: flex;
  flex-direction: column;
  justify-content:flex-start;
  width: 300px ;
  

}

.about-picture{
  display: flex;
  width: 200px;
  height: auto;
  object-fit: cover;
  border-radius: 50%;
  box-sizing: border-box;
  border : 2px solid black;
  box-shadow: 10px 5px 5px black;
}

.about-picture img {
  width: 200px;
  height: auto;
  object-fit: cover;
  border-radius: 50%;
  box-sizing: border-box;
  border : 2px solid black;
  box-shadow: 10px 5px 5px black;
}
  


.about>* {
  width: 200px;
  

  
}

#works {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items:center;
  gap: 30px;

}


img {
  width: 200px;
  height: auto;
  /*object-fit: cover;
  border-radius: 50%;
  box-sizing: border-box;*/
  border : 2px solid black;}

img:hover {
  box-shadow: 10px 5px 5px black;
}


</style>
