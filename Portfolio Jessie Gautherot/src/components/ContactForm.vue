<script setup>
import { ref } from 'vue';

</script>

<template>
  <form  @submit.prevent="onSubmit">
   <label for="firstname">Prénom:</label>
   <input type="text" name="firstname" id="firstname" v-model="firstname"><br>
   <label for="lastname">Nom:</label>
   <input type="text" name="lastname" id="lastname" v-model="lastname"><br>
   <label for="email">E-mail:</label>
   <input type="email" name="email" id="email" v-model="email"><br>
   <label for="message">Votre message:</label>
   <input type="textarea" name="message" id="message" v-model="message"><br>
   <button type="submit">Envoyer</button>
  </form>
  <p v-if="messageEnvoye">Votre message a bien été envoyé !</p>
</template>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>