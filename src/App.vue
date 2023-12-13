<script setup>
    import { RouterView } from "vue-router"
    import Header from './components/Header.vue'
</script>

<template>
    <Header />
    <main id="main">
        <RouterView />
    </main>
    <footer>
        <div>
            <a href="https://linkedin.com/in/alainfreelance" target="_blank"><img src="./assets/img/logo/linkedin.png" alt="Logo de LinkedIn"></a>
            <a href="https://github.com/AlaiWebDev" target="_blank"><img src="./assets/img/logo/github.png" alt="Logo de GitHub"></a>
            <a href="https://mail.google.com/mail/u/0/#inbox?compose=new" target="_blank"><img src="./assets/img/logo/mail.png" alt="Logo de Google Mail"></a>
        </div>
        <small>
            &copy;<time datetime="2023-12-06"> 06/12/2023</time>
        </small>
    </footer>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@300&family=Open+Sans&display=swap');
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    font-size: 20px;
    color: bisque;
    font-family: 'Open Sans', sans-serif;
}
body {
    background-color: #733C4A;
}
main {
    min-height: 100vh;
    padding-top: 30px;
    background-color: #733C4A;
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
    background-color:#010440 ;
}
footer div {
    padding: .5rem;
    border-radius: 1rem;
    background-color:rgba(255, 255, 255, 0.116) ;
}
small {
    justify-self: flex-start;
}
</style>

