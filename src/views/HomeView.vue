<script setup lang="ts">
import Modal from '../components/ModalComp.vue'
import { ref } from 'vue'

const showModal = ref<boolean>(false)

function toggleModal() {
  showModal.value = !showModal.value
}

function closeModal() {
  showModal.value = false
}
</script>

<template>
  <div>
    <div class="container">
      <h1>Teleporting Components</h1>
      <button class="btn" @click="toggleModal">Open Modal</button>
    </div>
    <!-- Teleport the modal to the body of the document -->
    <teleport to="body">
      <Modal v-if="showModal" @close="closeModal" />
    </teleport>
  </div>
</template>

<style scoped>
.container {
  text-align: center;
  padding-top: 20px;

}

.btn {
  padding: 12px 24px;
  margin-top: 20px;
}
</style>
