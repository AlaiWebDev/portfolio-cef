<script setup>
import { ref } from "vue";
import Work from './Work.vue';
import datasProjects from '@/assets/datas/datas.json';
const works = ref(datasProjects);
</script>
<template>
  <section id="my_works">
    <h2>Mes réalisations</h2>
    <article v-for="work in works" :key="work.id">
      <Work :work="work" />
    </article>
  </section>
</template>

<style scoped>
section {
  width: fit-content;
  margin: auto;
}
article {
  margin: auto;
  margin-bottom: 2rem;
  border: 1px solid #733c4a;
  
}
article:hover {
  border: 1px solid white;
  box-shadow: 19px 19px 15px -3px rgba(1, 4, 65,0.3);
}
</style>
