<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <div>
        <label for="email">Email</label>
        <input type="email" v-model="form.email" required />
      </div>
      <div>
        <label for="message">Message</label>
        <textarea v-model="form.message" required></textarea>
      </div>
      <button type="submit">Envoyer</button>
    </form>

    <!-- Affichage du statut -->
    <div v-if="statusMessage" :class="statusClass">{{ statusMessage }}</div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const form = ref({
      email: '',
      message: '',
    });

    const statusMessage = ref('');
    const statusClass = ref('');

    const handleSubmit = () => {
      const formData = {
        email: form.value.email,
        message: form.value.message,
      };

      // Récupérer l'adresse email définie dans le fichier .env
      const simulatedEmail = import.meta.env.VITE_APP_EMAIL_FICTIF;

      // Simuler l'envoi de l'email vers l'adresse définie en variable d'environnement
      if (formData.email && formData.message) {
        // Simuler un "envoi" vers l'adresse définie en .env
        setTimeout(() => {
          statusMessage.value = `L'email aurait été envoyé à ${simulatedEmail} (Simulation)`;
          statusClass.value = 'success';
        }, 1000);
      } else {
        statusMessage.value = "Veuillez remplir tous les champs.";
        statusClass.value = 'error';
      }
    };

    return {
      form,
      statusMessage,
      statusClass,
      handleSubmit,
    };
  },
};
</script>

<style scoped>
.success {
  color: green;
}
.error {
  color: red;
}
</style>

