<script setup>
    import { ref } from 'vue'
    import MyModal from '../components/modals/MyModal.vue'
    const works = ref([
        {
        nom: "DWWM-ID-Formation-Strasbourg",
            date: "03/2022-11/2022",
            apprenants: 12,
            image: "work-1"
        },
        {
            nom: "DWWM-AFPA-Angers",
            date: "09/2023-09/2023",
            apprenants: 11,
            image: "work-2"
        },
        {
            nom: "DWWM-AFPA-Marseille",
            date: "09/2023-11/2023",
            apprenants: 17,
            image: "work-3"
        }
    ])
    const itemToDisplay = ref(null);
    const isModalOpened = ref(false);
    const openModal = (e) => {
        itemToDisplay.value = e.target.id;
        isModalOpened.value = true;
    };
    const closeModal = () => {
        isModalOpened.value = false;
    };
</script>
<template>
    <h2 id="my_works">Mes réalisations</h2>
    <section v-for="(work, index) in works">
        <h3>{{ work.nom }}</h3>
        <button @click="openModal"><img :src="`../../public/${work.image}.jpg`" :id="index" :alt="`${work.image}`"></button>
        <MyModal :to-display="Number(itemToDisplay)" :jobs="works" :isOpen="isModalOpened" @modal-close="closeModal" name="first-modal">
            <template #header>
            </template>
            <template #content>
            </template>
            <template #footer>
            </template>
        </MyModal>
    </section>
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

@media screen and (max-width: 1024px) {

    }
</style>
