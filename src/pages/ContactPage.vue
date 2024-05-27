<template>
  <div class="content">
    <img src="/Untitled00180002.png" alt="">
    <div class="contact">
      <div class="info">
      </div>
      <form ref="form" @submit.prevent="sendMail">
        <div class="user-information">
          <InputText type="text" title="Nom Prénom" id="name"></InputText>
          <InputText type="mail" title="Mail" id="reply_to"></InputText>
        </div>
        <InputText type="text" title="Objet" id="objet"></InputText>
        <InputText type="text" title="Message" id="message" long="true"></InputText>
        <div class="send">
          <button type="submit">Envoyer</button>
          <p class="sendResult" :class="[isSuccesSend ? 'success' : 'failed']">{{ sendResult }}</p>
        </div>
      </form>
    </div>

  </div>
</template>

<script setup lang="ts">

import InputText from '../components/InputText.vue'
import emailjs from '@emailjs/browser';

import {ref} from 'vue';

const sendResult = ref("");
const isSuccesSend = ref(false);

const sendMail = () => {
  const form = document.querySelector('form') as HTMLFormElement;
  emailjs.sendForm('service_rmv02p4', 'template_1peao9h', form, 'A6Y75-PLLNQbiQeOu')
    .then(
      () => {
        isSuccesSend.value = true;
        sendResult.value = 'Votre message a été envoyé avec succès !';
        form.reset();
      },
      (error) => {
        isSuccesSend.value = false;
        console.log('ERROR...', error.text);
        sendResult.value = 'Erreur lors de l\'envoi du mail !';
      }
    );
  };

</script>

<script lang="ts">

export default {
  methods: {
    
    },
};
</script>

<style scoped>

.content {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 86dvh;
    background-color: #1F1F29;
    overflow: hidden;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    display: flex;
}

img {
    position: absolute;
    z-index: 1;
    filter: blur(4px) opacity(10%);
    opacity: 90%;
    bottom: 0;
}

.contact {
  z-index: 2;
  margin-bottom: -8%;
  height: 70%;
  display: flex;
  flex-direction: row;
  padding: 2px;
  align-self: center;
  justify-self: center;
  border-radius: 10px;
  background-color: #c9c9c9b9;
}

.info {
  flex: 1;
  background-color: #00B578;
  border-radius: 10px;
}

.info h1 {
  color: white;
  font-size: 24px;
  margin: 40px 0px 0px 40px;
}

.info p {
  color: white;
  font-size: 20px;
  margin-left: 40px;
}

form {
  margin: 4dvw;
  display: flex;
  flex-direction: column;
  gap: 1dvw;
  flex: 2;
}

.send {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 10px;
}

.success {
  color: #00B578;
}

.failed {
  color: red;
}

button {
  background-color: #00B578;
  border: none;
  border-radius: 10px;
  padding: 15px 30px;
  font-size: 18px;
}

.user-information {
  display: flex;
  flex-direction: row;
  column-gap: 2dvw;
}
</style>