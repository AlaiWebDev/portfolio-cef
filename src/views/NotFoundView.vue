<template>
    <h1>404</h1>
    <img src="../assets/img/404.jpg" alt="Image de  la page 404">
    <h2>La page que vous demandez n'existe pas</h2>
    <RouterLink to="/">Retour</RouterLink>
</template>

<script setup>
import { RouterLink } from "vue-router";

</script>

<style scoped>
    *{
        margin: auto;
    }
    h1 {
        width: fit-content;
        margin: auto;
        margin-top: 3rem;
        font-size: 6rem;
    }
    img {
        display: block;
        margin-bottom: 2rem;
    }
    h2 {
        margin-bottom: 1rem;
    }
    a {
        display: block;
        width: fit-content;
        text-decoration: none;
        padding: .5rem;
        background-color: bisque;
        color: #010326;
    }
</style>