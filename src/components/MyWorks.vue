<script setup>
    import { ref } from 'vue'
    import MyModal from '../components/modals/MyModal.vue'
    const works = ref([
        {
            id: 1,
            nom: "DWWM-ID-Formation-Strasbourg",
            date: "03/2022-11/2022",
            apprenants: 12,
            image: "work-1"
        },
        {
            id: 2,
            nom: "DWWM-AFPA-Angers",
            date: "09/2023-09/2023",
            apprenants: 11,
            image: "work-2"
        },
        {
            id: 3,
            nom: "DWWM-AFPA-Marseille",
            date: "09/2023-11/2023",
            apprenants: 17,
            image: "work-3"
        }
    ])
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
    <div id="my_works">
        <h2>Mes réalisations</h2>
        <section v-for="work  in works" :key="work.id">
            <h3>{{ work.nom }}</h3>
            <button @click="openModal(work)">
                <img :src="`../../src/assets/img/${work.image}.jpg`" :alt="`${work.image}`">
            </button>
            <MyModal :currentProject="selectedProject" :isOpen="isModalOpened" @modal-close="closeModal" name="first-modal">
                <template #header>
                </template>
                <template #content>
                </template>
                <template #footer>
                </template>
            </MyModal>
        </section>
    </div>
</template>
<style scoped>

div {
    margin-bottom: 2rem;
}

h3:first-of-type {
    margin-top: 1rem;
}

h3 {
    width: fit-content;
    margin: auto;
    margin-top: .5rem;
    font-size: .7rem;
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
