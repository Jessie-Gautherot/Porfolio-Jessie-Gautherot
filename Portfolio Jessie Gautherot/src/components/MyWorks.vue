<template>
  <div class="works-list">
    
    
    <!-- Projet 1 (CV) -->
    <div class="work-item" @click="openModal('cv')">
      <h2>Mon CV en HTML et CSS</h2>
      <figure>
        <img src="@/assets/image cv 2.png" alt="Mon CV réalisé en HTML et CSS" class="img">
      </figure>
    </div>

    <!-- Projet 2 (Cahier des Charges) -->
    <div class="work-item" @click="openModal('cahier')">
      <h2>Mon cahier des charges</h2>
      <figure>
        <img src="@/assets/picture-cahier-des-charges.png" alt="Cahier des charges pour un projet web" class="img">
      </figure>
    </div>

    <!-- Projet 3 (Espace Commentaire) -->
    <div class="work-item" @click="openModal('commentaire')">
      <h2>Dynamisme d'un espace commentaire en Javascript</h2>
      <figure>
        <img src="@/assets/picture-javascript.png" alt="Espace commentaire dynamique en Javascript" class="img">
      </figure>
    </div>

    <!-- La modale -->
    <div v-if="isModalOpen" class="modal-overlay" @click.self="closeModal">
      <div class="modal">
        <button class="close-modal" @click="closeModal">X</button>
        <h2>{{ modalTitle }}</h2>
        <p><strong>Date de création :</strong> {{ modalDate }}</p>
        <p><strong>Technologies utilisées :</strong> {{ modalTechnologies }}</p>

    <!--div à afficher, seulement si une valeur est assignée-->
        <div v-if="modalLink">
          <p><a :href="modalLink" target="_blank">Visiter le projet</a></p>
        </div>

        <div v-if="modalGithub">
          <p><a :href="modalGithub" target="_blank">Voir le repository GitHub</a></p>
        </div>
        
        <div v-if="modalImage">
          <img :src="modalImage" alt="Image du projet" class="modal-img">
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Données de la modale
const isModalOpen = ref(false);
const modalTitle = ref('');
const modalDate = ref('');
const modalTechnologies = ref('');
const modalLink = ref('');
const modalGithub = ref('');
const modalImage = ref(''); 

// Fonction pour ouvrir la modale avec les informations dynamiques
const openModal = (project) => {
  isModalOpen.value = true;

// Définir les informations qui apparaissent en fonction du projet
  if (project === 'cv') {
    modalTitle.value = 'Mon CV en HTML et CSS';
    modalDate.value = 'Septembre 2024';
    modalTechnologies.value = 'HTML, CSS';
    modalLink.value = '/index-cv.html';
    modalGithub.value = 'https://github.com/Jessie-Gautherot/CV'; 
    modalImage.value = '/cv-picture.png'; 

  } else if (project === 'cahier') {
    modalTitle.value = 'Mon cahier des charges';
    modalDate.value = 'Novembre 2024';
    modalTechnologies.value = 'OpenOffice, PDF';
    modalLink.value = '/cahier-des-charges.pdf'; 
    modalGithub.value=''; // pas de repository pour ce projet
    modalImage.value = ''; // Pas d'image pour ce projet

  } else if (project === 'commentaire') {
    modalTitle.value = 'Dynamisme d\'un espace commentaire en Javascript';
    modalDate.value = 'Décembre 2024';
    modalTechnologies.value = 'Javascript';
    modalLink.value = '/index-commentaire.html';
    modalGithub.value = 'https://github.com/Jessie-Gautherot/espace-commentaire'; 
    modalImage.value = '/commentaire-picture.png'; 
  }
};

// Fonction pour fermer la modale
const closeModal = () => {
  isModalOpen.value = false;
};
</script>

<style scoped>


h2 {
  color: #35434b;
  font-size: 1.3rem;
}

.works-list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.work-item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-bottom: 20px;
  cursor: pointer;
}

.img {
  width: 200px;
  height: auto;
  border: 2px solid black;
}

.img:hover {
  box-shadow: 10px 5px 5px #35434b;
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal {
  background-color: #ffdb9e;
  padding: 20px;
  border-radius: 8px;
  max-width: 600px;
  width: 80%;
  text-align: center;
  position: relative;
  max-height: 80vh;
  overflow-y: auto;
}

.close-modal {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 24px;
  background: none;
  border: none;
  color: #35434b;
  cursor: pointer;
}


.modal-img {
  max-width: 100%;
  max-height: 300px;
}

a {
  color: #35434b;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
</style>


