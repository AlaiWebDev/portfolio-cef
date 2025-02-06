<script setup>
import { ref } from "vue";
import Work from './Work.vue';
import datasProjects from '@/assets/datas/datas.json';
const works = ref(datasProjects);
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
