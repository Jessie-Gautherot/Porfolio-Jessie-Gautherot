<script setup>
import { ref } from 'vue';

const showMessageError = ref (false)

const myFictifEmail = process.env.VUE_APP_EMAIL_FICTIF || 'jessie.gautherot@wanadoo.com'

const recep = ref ({
  firstname : (''),
  lastname : (''),
  email : (''),
  message : (''),
})

function ClearForm () {
  firstname.value = '',
  lastname.value = '',
  email.value = '',
  message.value =''
}

function SendMail (recep) {
  if (recep.firstname.length<1
  || recep.lastname.length<1
  || recep.email.length<1
  || recep.message.length<1){
    showMessageError.value = true
  } else {
    showMessageError.value = false
    }
     // Send Form
     console.log ('envoyé !')
    // and delete Form
    ClearForm ()
  }



</script>

<template>
  <div class="MessageError" v-if="showMessageError">
   <p>Tous les champs doivent être renseignés</p>
  </div>
  <form  @submit.prevent="onSubmit">
   <label for="firstname">Prénom:</label>
   <input type="text" name="firstname" id="firstname" v-model="recep.firstname"><br>
   <label for="lastname">Nom:</label>
   <input type="text" name="lastname" id="lastname" v-model="recep.lastname"><br>
   <label for="email">E-mail:</label>
   <input type="email" name="email" id="email" v-model="recep.email"><br>
   <label for="message">Votre message:</label>
   <input type="textarea" name="message" id="message" v-model="recep.message"><br>
   <button @click="SendMail"(recep) type="submit">Envoyer</button>
  </form>
  <p v-if="messageEnvoye">Votre message a bien été envoyé à {{ myFictifEmail }}</p>
</template>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>