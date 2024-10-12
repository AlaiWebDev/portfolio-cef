<script setup>
import MyModal from "../components/modals/MyModal.vue";
import { ref } from "vue";
defineProps({
    work: {
        type: Object
    }
})
const selectedProject = ref({});
const isModalOpened = ref(false);

const openModal = (work) => {
  selectedProject.value = work;
  isModalOpened.value = true;
};
const closeModal = () => {
  isModalOpened.value = false;
};
</script>
<template>
    <h3>{{ work.nom }}</h3>
    <button @click="openModal(work)">
        <img
        :src="`./src/assets/img/${work.image}.jpg`"
        :alt="`${work.image}`" />
    </button>
    <MyModal
        :currentProject="selectedProject"
        :isOpen="isModalOpened"
        @modal-close="closeModal"
        name="first-modal"
    >
        <template #header> </template>
        <template #content> </template>
        <template #footer> </template>
    </MyModal>
</template>
<style scoped>
h3:first-of-type {
  margin-top: 1rem;
}

h3 {
  width: fit-content;
  margin: auto;
  margin-top: 0.5rem;
  font-size: 0.7rem;
}

button {
  display: block;
  width: fit-content;
  margin: auto;
  margin-top: 1rem;
}

img {
  display: block;
  width: 350px;
  height: 200px;
  margin: auto;
}
</style>