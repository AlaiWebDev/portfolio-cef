<script setup>
import { ref } from "vue";
import Work from './Work.vue';
const works = ref([
  {
    id: 1,
    nom: "DWWM-ID-Formation-Strasbourg",
    date: "03/2022-11/2022",
    apprenants: 12,
    image: "work-1",
  },
  {
    id: 2,
    nom: "DWWM-AFPA-Angers",
    date: "09/2023-09/2023",
    apprenants: 11,
    image: "work-2",
  },
  {
    id: 3,
    nom: "DWWM-AFPA-Marseille",
    date: "09/2023-11/2023",
    apprenants: 17,
    image: "work-3",
  },
]);
</script>
<template>
  <div id="my_works">
    <h2>Mes réalisations</h2>
    <section v-for="work in works" :key="work.id">
      <Work :work="work" />
    </section>
  </div>
</template>

<style scoped>
div {
  width: fit-content;
  margin: auto;
}
section {
  margin: auto;
  margin-bottom: 2rem;
  border: 1px solid #733c4a;
  
}
section:hover {
  border: 1px solid white;
  box-shadow: 19px 19px 15px -3px rgba(1, 4, 65,0.3);
}
</style>
