<script setup>

</script>

<template>
    <div id="contact">
        <h2>Me contacter</h2>
        <form @submit.prevent>
            <label>
                Nom
                <input type="text" name="" id="">
            </label>
            <label>
                Prénom
                <input type="text" name="" id="">
            </label>
            <label>
                Adresse e-mail
                <input type="text" name="" id="">
            </label>
            <label>
                Message
                <textarea name="" id="" cols="30" rows="10"></textarea>
            </label>
            <input type="submit" value="Envoyer">
        </form>
    </div>
</template>

<style scoped>
form {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    width: 50%;
    height: 60vh;
    padding: 1.5rem;
    margin: auto;
    border: 1px solid #D9A78B;
    box-shadow: 19px 19px 15px -3px rgba(1, 4, 65,0.3);
}
label {
    display: flex;
    justify-content: space-between;
    width: 35%;
    text-align: left;
}
label:last-of-type {
    display: flex;
    justify-content: space-evenly;
    width: 60%;
}
input[type='text'] {
    border: 2px solid #D9A78B;
    color: #010440;
    font-weight: 800;
}
textarea {
    width: 80%;
    height: 10rem;
    resize: none;
    font-weight: 800;
    font-style: italic;
    color: rgb(0, 2, 41);
    border: 2px solid #D9A78B;
}
input[type='submit'] {
    padding: .5rem;
    color: #010326;
}
@media screen and (max-width: 1024px) {
    form {
        width: 90%;
    }
    label {
        width: 50%;
    }
    }
</style>