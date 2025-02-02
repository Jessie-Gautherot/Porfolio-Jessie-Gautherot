<template>
  <!-- Affiche le modale si isOpen est vrai-->
  <div v-if="props.isOpen" class="modal-mask">
    <!-- Pour centrer à l'écran-->
    <div class="modal-wrapper">
      <!--Conteneur de la modale-->
      <div class="modal-container" ref="target">
        <div class="modal-header">
          <!--header, content and footer depending of the project with slot-->
          <slot name="header">default header</slot>
        </div>
        <div class="modal-body">
          <slot name="content">default content</slot>
        </div>
        <div class="modal-footer">
          <slot name="footer">
            <!--Fermeture de la modale au clic-->
            <button @click.stop="emit('modal-close')">Close</button>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from 'vue';
import { onClickOutside } from '@vueuse/core';

// Constante isOpen qui vérifie si la modale est ouverte ou non
const props = defineProps({
  isOpen: Boolean
});
// Fermer la modale
const emit = defineEmits(['modal-close']);
// En cas de clic en dehors de la modale, celle-ci se ferme
const target = ref(null);
onClickOutside(target, () => emit('modal-close'));
</script>

<style scoped>
/*Arrière plan foncé et transparent de la modale*/
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}
/* Centrer la modale*/
.modal-wrapper{
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 9999; 
}
/* conteneur des éléments*/
.modal-container {
  background-color: #ffdb9e;
  border-radius: 8px;
  padding: 30px;
  max-width: 400px; 
  width: 60%; 
  max-height: 90vh;  
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  text-align: center;
  position: relative;
  margin: 0 auto; 
}
/* Taille des images de la modale*/
.modal-container img {
  max-width: 40%;
  height: auto;
}

</style>