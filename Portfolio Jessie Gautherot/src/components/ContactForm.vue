<template>
  <!--Création d'un formulaire et empechement du comportement par defaut, pour ne pas que la page se recharge-->
  <form @submit.prevent="handleSubmit">
    <div>
      <label for="firstname">Prénom</label>
      <!--utilisation de v-model pour lier les données à une classe dynamique pour l'affichage des erreurs-->
      <input type="text" id="firstname" v-model="form.firstname":class="{'error': errors.firstname}">
      <div v-if="errors.firstname" class="error-message">{{ errors.firstname }}</div>
    </div>
    <div>
      <label for="lastname">Nom</label>
      <input type="text" id="lastname" v-model="form.lastname":class="{'error': errors.lastname}">
      <div v-if="errors.lastname" class="error-message">{{ errors.lastname }}</div>
    </div>
    <div>
      <label for="object">Objet</label>
      <input type="text" id="object" v-model="form.object" :class="{'error': errors.object}">
      <div v-if="errors.object" class="error-message">{{ errors.object }}</div>
    </div>
    <div>
      <label for="message">Message</label>
      <textarea id="message" v-model="form.message":class="{'error': errors.message}"></textarea>
      <div v-if="errors.message" class="error-message">{{ errors.message }}</div>
    </div>
    <div>
      <button type="submit">Envoyer</button>
    </div>
  </form>
</template>

<script setup>
import { ref } from 'vue';
// Variables réactives pour les champs du formulaire, avec des valeurs vides, par défaut
const form = ref({
  firstname: '',
  lastname: '',
  object: '',
  message: '',
});
// Variable réactives pour stocker les messages d'erreurs, associés à chaque champs du formulaire
const errors = ref({
  firstname: '',
  lastname: '',
  object: '',
  message: '',
});
// Fonction de soumission du formulaire
const handleSubmit = () => {
  // Réinitialiser les erreurs avant validation, pour eviter d'afficher les erreurs d'une précédente soumission
  errors.value = {
    firstname: '',
    lastname: '',
    object: '',
    message: '',
  };
  // Variable pour suivre l'état de validation du formulaire
  let isValid = true;
  // Vérifier si tous les champs sont remplis. Si un champs est vide, une erreur est enregistrée
  // pour ce champ et "isValid" est mit à false
  if (!form.value.firstname) {
    errors.value.firstname = 'Le prénom est requis.';
    isValid = false;
  }

  if (!form.value.lastname) {
    errors.value.lastname = 'Le nom est requis.';
    isValid = false;
  }

  if (!form.value.object) {
    errors.value.object = 'L\'objet est requis.';
    isValid = false;
  }

  if (!form.value.message) {
    errors.value.message = 'Le message est requis.';
    isValid = false;
  }
  // Si tous les champs sont rempli, appeler "sendContactForm"
  if (isValid) {
    sendContactForm();
  }
};
// Fonction qui 
// simule l'envoi de l'email vers une adresse fictive, définie en variable d'environement
// affiche une fenêtre, montrant que le formulaire à bien été envoyé
// réinitialise les champs du formulaire après l'envoi simulé
const sendContactForm = () => {
  const FictifEmail = import.meta.env.VITE_EMAIL_FICTIF;

  alert(`Votre demande a bien été envoyée à ${FictifEmail}`);
  
  form.value.firstname = '';
  form.value.lastname = '';
  form.value.object = '';
  form.value.message = ''; 
};
</script>

<style scoped>
.error {
  border-color: gray;
}

.error-message {
  color: rgb(175, 46, 46);
  font-size: 12px;
}

form {
  display: flex;
  flex-direction: column; 
  gap: 8px;
  width: 300px; 
  margin: auto; 
  padding: 50px;
  padding-right: 70px;
  border: 1px solid #e47a51;
  border-radius: 8px;
  background-color: #f9f9f9;
}

label {
  font-size: 1rem;
  margin-bottom: 0.5rem;
  color: #35434b;
}

input, textarea {
  padding: 0.8rem;
  border: 1px solid #b9b8b8;
  border-radius: 4px;
  font-size: 1rem;
  width: 100%;
}

button {
  padding: 1rem;
  background-color: #35434b;
  color: #ffdb9e;
  border: 1px black;
  border-radius: 4px;
  font-size: 1rem;
  cursor: pointer;
}

button:hover {
  background-color: #e47a51; 
}
</style>
