<template>
  <div class="content">
    <div class="contact">
      <div class="info">
        <h1>Contactez moi</h1>
        <p>06.82.54.68.06</p>
        <p>mace.leo33@gmail.com</p>
      </div>
      <form action="">
        <div class="user-information">
          <InputText type="text" title="Nom Prénom" id="np"></InputText>
          <InputText type="mail" title="Mail" id="mail"></InputText>
        </div>
        <InputText type="text" title="Objet" id="objet"></InputText>
        <InputText type="text" title="Message" id="message" long="true"></InputText>
        <div class="send">
          <button type="submit">Envoyer</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import InputText from '../components/InputText.vue'
</script>

<style scoped>

.content{
  display: flex;
  height: 77.5dvh;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.contact {
  display: flex;
  flex-direction: row;
  width: 50dvw;
  padding: 2px;
  aspect-ratio: 16/8;
  align-self: center;
  justify-self: center;
  border-radius: 22px;

  box-shadow: 2px -1px 7px 3px #c9c9c956;
  -webkit-box-shadow: 2px -1px 7px 3px #c9c9c956;
  -moz-box-shadow: 2px -1px 7px 3px #c9c9c956;
}

.info {
  flex: 1;
  background-color: #00B578;
  border-radius: 20px;
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