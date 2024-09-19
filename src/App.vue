<script setup>
import { RouterView } from "vue-router";
import Header from "./components/MyHeader.vue";
import Footer from "./components/MyFooter.vue"; 
</script>

<template>
  <Header />
  <main id="main">
    <RouterView />
  </main>
  <Footer />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Lato:wght@300&family=Open+Sans&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-size: 20px;
  color: bisque;
  font-family: "Open Sans", sans-serif;
}

body {
  background-color: #733c4a;
}

main {
  min-height: 100vh;
  padding-top: 30px;
  background-color: #733c4a;
}

h2 {
  width: fit-content;
  margin: auto;
  margin-top: 100px;
  margin-bottom: 20px;
}

footer {
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #010440;
}

footer div {
  padding: 0.5rem;
  border-radius: 1rem;
  background-color: rgba(255, 255, 255, 0.116);
}

footer a img {
  border-radius: 50%;
  margin: auto 5px;
}

footer a:hover img {
  box-shadow: 0 0 6px 6px bisque;
}

small {
  justify-self: flex-start;
}
</style>
