<script setup>
    import { ref } from 'vue'
    import MyModal from '../components/modals/MyModal.vue'
    import MyModal2 from '../components/modals/MyModal2.vue'
    import MyModal3 from '../components/modals/MyModal3.vue'

    // const works = ref([
    //     {
    //         nom: "DWWM-ID-Formation-Strasbourg",
    //         date: "03/2022-11/2022",
    //         apprenants: 12,
    //         image: "work-1"
    //     },
    //     {
    //         nom: "DWWM-AFPA-Angers",
    //         date: "09/2023-09/2023",
    //         apprenants: 11,
    //         image: "work-2"
    //     },
    //     {
    //         nom: "DWWM-AFPA-Marseille",
    //         date: "09/2023-11/2023",
    //         apprenants: 17,
    //         image: "work-3"
    //     },
    // ])
    const work1 = ref({
        nom: "DWWM-ID-Formation-Strasbourg",
            date: "03/2022-11/2022",
            apprenants: 12,
            image: "work-1"
    })
    const work2 = ref({
        nom: "DWWM-AFPA-Angers",
        date: "09/2023-09/2023",
        apprenants: 11,
        image: "work-2"
    })
    const work3 = ref({
        nom: "DWWM-AFPA-Marseille",
        date: "09/2023-11/2023",
        apprenants: 17,
        image: "work-3"
    })
    const isModalOpened = ref(false);
    const isModal2Opened = ref(false);
    const isModal3Opened = ref(false);

    const openModal = () => {
    isModalOpened.value = true;
    };
    const closeModal = () => {
    isModalOpened.value = false;
    };
    const openModal2 = () => {
    isModal2Opened.value = true;
    };
    const closeModal2 = () => {
    isModal2Opened.value = false;
    };
    const openModal3 = () => {
    isModal3Opened.value = true;
    };
    const closeModal3 = () => {
    isModal3Opened.value = false;
    };
</script>
<template>
    <!-- <div v-for="(work, index) in works" :key="index"> -->
    <h3>{{ work1.nom }}</h3>
        <button @click="openModal"><img :src="`../../public/${work1.image}.jpg`" :alt="`${work1.image}`"></button>
        <MyModal :work-item="work1" :isOpen="isModalOpened" @modal-close="closeModal" name="first-modal">
            <template #header>
            </template>
            <template #content>
            </template>
            <template #footer>
            </template>
        </MyModal>
    <h3>{{ work2.nom }}</h3>
        <button @click="openModal2"><img :src="`../../public/${work2.image}.jpg`" :alt="`${work2.image}`"></button>
        <MyModal2 :work-item="work2" :isOpen="isModal2Opened" @modal-close="closeModal2" name="first-modal">
            <template #header>
            </template>
            <template #content>
            </template>
            <template #footer>
            </template>
        </MyModal2>
    <h3>{{ work3.nom }}</h3>
        <button @click="openModal3"><img :src="`../../public/${work3.image}.jpg`" :alt="`${work3.image}`"></button>
        <MyModal3 :work-item="work3" :isOpen="isModal3Opened" @modal-close="closeModal3" name="first-modal">
            <template #header>
            </template>
            <template #content>
            </template>
            <template #footer>
            </template>
        </MyModal3>
</template>
<style scoped>
* {
    color: #010440;
}
div:first-of-type {
    margin-top: 4rem;
}

div {
    margin-bottom: 2rem;
}
h3:first-of-type {
    margin-top: 4rem;
}
h3 {
    width: fit-content;
    margin: auto;
    margin-top: .5rem;
    font-size: .7rem;
}

button {
    display: block;
    width: 250px;
    margin: auto;
    margin-top: 1rem;  
}
img {
    display: block;
    width: 246px;
    height: 150px;
    margin: auto;
}

@media screen and (max-width: 1024px) {

    }
</style>
