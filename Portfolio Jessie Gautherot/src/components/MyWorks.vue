<template>
  <div class="works-list">
    <!-- Projet 1 (CV) -->
    <!-- Au clic, la fonction openModal est appelée avec l'argument CV et affiche les informations de ce projet-->
    <div class="work-item" @click="openModal('cv')">
      <h2>Mon CV en HTML et CSS</h2>
      <figure>
        <img src="@/assets/image cv 2.png" alt="Mon CV réalisé en HTML et CSS" class="img">
      </figure>
    </div>
    <!-- Projet 2 (Cahier des charges) -->
    <!-- Au clic, la fonction openModal est appelée avec l'argument cahier et affiche les informations de ce projet-->
    <div class="work-item" @click="openModal('cahier')">
      <h2>Mon cahier des charges</h2>
      <figure>
        <img src="@/assets/picture-cahier-des-charges.png" alt="Cahier des charges pour un projet web" class="img">
      </figure>
    </div>
    <!-- Projet 3 (Espace commentaire) -->
    <!-- Au clic, la fonction openModal est appelée avec l'argument commentaire et affiche les informations de ce projet -->
    <div class="work-item" @click="openModal('commentaire')">
      <h2>Dynamisme d'un espace commentaire en Javascript</h2>
      <figure>
        <img src="@/assets/picture-javascript.png" alt="Espace commentaire dynamique en Javascript" class="img">
      </figure>
    </div>
    <!-- Modal -->
    <!--Le composant "ModalComponent" est affiché ou non en fonction de la valeur de "isModalOpen"-->
    <!--Ecoute de l'évenement "modal-close" émit par le composant "ModalComponent" pour fermer la modale-->
    <ModalComponent :isOpen="isModalOpen" @modal-close="closeModal">
      <!--Affiche le titre dynamique du projet ouvert-->
      <template #header>
        <h2>{{ modalTitle }}</h2>
      </template>
      <!--Affiche le contenu dynamique du projet ouvert-->
      <template #content>
        <p><strong>Date de création :</strong> {{ modalDate }}</p>
        <p><strong>Technologies utilisées :</strong> {{ modalTechnologies }}</p>
        <!--Affiche le contenu dynamique du projet ouvert, seulement si une valeur est assignée-->
        <div v-if="modalLink">
          <p><a :href="modalLink" target="_blank">Visiter le projet</a></p>
        </div>
        <div v-if="modalGithub">
          <p><a :href="modalGithub" target="_blank">Voir le repository GitHub</a></p>
        </div>
        <div v-if="modalImage">
          <img :src="modalImage" alt="Image du projet" class="modal-img">
        </div>
      </template>
      <template #footer>
        <!--bouton de fermeture dans le composant "ModalComponent"-->
      </template>
    </ModalComponent>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ModalComponent from './ModalComponent.vue';

// Constantes de la modale
const isModalOpen = ref(false);
const modalTitle = ref('');
const modalDate = ref('');
const modalTechnologies = ref('');
const modalLink = ref('');
const modalGithub = ref('');
const modalImage = ref('');

// Ouvrir la modale avec les informations dynamiques
const openModal = (project) => {
  isModalOpen.value = true;

// Informations en fonction du projet ouvert
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
    modalGithub.value = '';
    modalImage.value = ''; 

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

.modal-img {
  max-width: 70%;
  max-height: 40vh;
}

a {
  color: #35434b;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
</style>
