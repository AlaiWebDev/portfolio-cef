<script setup>
import emailjs from '@emailjs/browser';
const emailAddress = import.meta.env.VITE_EMAIL_ADRESS;
    function sendEmail() {
        alert("Le message a bien été envoyé à " + emailAddress);
        // (() => {
        //   emailjs.init(import.meta.env.VITE_EMAILJS_PUBLIC_KEY);
        // })();
        // const params = {
        //     to_name: "Alain",
        //     from_name: document.querySelector("#senderName").value,
        //     from_email: document.querySelector("#senderEmail").value,
        //     message: document.querySelector("#emailMessage").value,
        //     reply_to: document.querySelector("#senderEmail").value
        // }
        // const serviceID = import.meta.env.VITE_EMAILJS_SERVICEID;
        // const templateID = import.meta.env.VITE_EMAILJS_TEMPLATEID;
        // emailjs.send(serviceID, templateID, params)
        // .then( res => {
        //     alert("L'e-mail a été envoyé avec succès");
        // })
        // .catch();
    }
</script>

<template>
    <section id="contact">
        <h2>Me contacter</h2>
        <form @submit.prevent="sendEmail()">
            <label>
                Nom complet
                <input type="text" name="" id="senderName">
            </label>
            <label>
                Adresse e-mail
                <input type="text" name="" id="senderEmail">
            </label>
            <label>
                Message
                <textarea name="" id="emailMessage" cols="30" rows="10"></textarea>
            </label>
            <input type="submit" value="Envoyer">
        </form>
    </section>
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