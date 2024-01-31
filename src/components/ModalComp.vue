<script setup lang="ts">
import { ref } from 'vue'
const showModal = ref<boolean>(true)



const emits = defineEmits(['close'])

function closeModal() {
  emits('close')
}
</script>

<template>
  <div v-if="showModal" class="modal-overlay">
    <div class="modal">
      <div class="modal-header">
        <h2>Modal Content</h2>
        <button @click="closeModal" class="close-button">Close</button>
      </div>
      <p>
        This is a modal component overlaying other content. his is a modal component overlaying
        other content.his is a modal component overlaying other content.his is a modal component
        overlaying other content.his is a modal component overlaying other content. his is a modal
        component overlaying other content. his is a modal component overlaying other content.
      </p>
    </div>
  </div>
</template>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background-color: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  max-width: 50%;
  margin: 0 auto;
}

.modal-header {
  display: flex;
  justify-content: space-between;
  justify-items: center;
  align-items: center;
  padding-bottom: 20px;
}

.close-button {
  background: rgb(209, 69, 69);
  border: none;
  width: 50px;
  color: white;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
