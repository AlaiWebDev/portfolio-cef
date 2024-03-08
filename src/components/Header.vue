<template>
    <header>
        <a href="#main"><img class="photo" src="../assets/img/logo/logo.png" alt="Photo de Alain ORLUK"></a>
            <h1>{{ title }}</h1>
            <a href="#" @click="toggle"  class="toggle-button">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
        </a>
        <ul v-if="show">
            <li><a href="#main">À propos de moi</a></li>
            <li><a href="#cv">Curriculum Vitae</a></li>
            <li><a href="#my_works">Réalisations</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </header>
</template>

<script setup>
    import {ref} from 'vue';
    
    const show = ref(true);
    const title = import.meta.env.VITE_APP_TITLE;
    function toggle(){
        show.value = !show.value
    }
    let windowWidth = window.innerWidth
    if(windowWidth<600){
        show.value = false
    }
</script>

<style scoped>
    header{
        display: flex;
        top: 0;
        left: 0;
        right: 0;
        justify-content: space-between;
        align-items: center;
        position: fixed;
        width: 100%;
        background-color:#010440 ;
        border-bottom: 1px solid black;
    }
    h1{
    width: fit-content;
    margin: auto;
    color: #733C4A;
}
    a:hover{
        background-color:#010440 ;
        /* font-weight: bold; */
        text-shadow:0px 0px 3px lightcoral;
    }
    .router-link-active{
        text-decoration: underline; 
        text-underline-offset: 8px;
    }
    .photo{
        width: 60px;
        height: 60px;
        margin: .5rem 2rem;
        object-fit: cover;
        border-radius: 50%;
        box-shadow: 0 0 30px white;
        background-color: white;
    }

    .photo:hover {
        box-shadow: 0 0 50px white;
    }
    header ul{
        display: flex;
        margin:0;
        padding:0;
        list-style-type: none;
    }
    header ul li a {
        padding: 1rem;
        display: block;
        color: #733C4A;
        text-decoration: none;
    }
    .toggle-button{
        position: absolute;
        display: none;
        top:.75rem;
        right: 1rem;
        flex-direction: column;
        justify-content: space-between;
        width: 30px;
        height: 20px;
    }
    .toggle-button .bar{
        height: 3px;
        width: 100%;
        background-color: white;
        border-radius: 10px;
    }
@media screen and (max-width: 600px) {
   .toggle-button{
        display: flex;
    } 
    header{
        flex-direction:column;
    }
    header ul{
        width: 100%;
        flex-direction: column;
    }
    header li {
        text-align: center;
    }
    header li a {
        padding: 5rem 1rem;
    }
    header .active{
        display: flex;
    }
}
</style>