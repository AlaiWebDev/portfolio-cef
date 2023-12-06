<script setup>

</script>

<template>
    <form @submit.prevent action="#" method="post">
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
</template>

<style scoped>
form {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    width: 60%;
    height: 70vh;
    padding: 2.5rem;
    margin: 5rem auto;
    border: 1px solid #D9A78B;
    box-shadow: 19px 19px 15px -3px rgba(1, 4, 65,0.3);
}
label {
    display: flex;
    justify-content: space-between;
    width: 40%;
    text-align: left;
}
input[type='text'] {
    border: 2px solid #D9A78B;
}
textarea {
    width: 70%;
    height: 10rem;
    color: #010326;
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