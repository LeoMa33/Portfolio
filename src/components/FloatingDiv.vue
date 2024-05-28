<template>
    <div ref="floating" :class="[isVisible ? 'floating' : 'hidden']">
        <img class="action" src="/fermer.png" alt="" @click="isVisible = false">
        <div class="content">
            <div class="top">
                <img class="illu" src="/megaphone.png" alt="">
                <h1>Recherche Une Alternance</h1>
            </div>
            <button @click="emit('changePage', 'Contact')">Me contacter</button>
        </div>
    </div>
</template>

<script setup lang="ts">

import {ref} from 'vue';

const emit = defineEmits(['changePage'])
const isVisible = ref(true);

</script>

<style scoped>

.floating {
    z-index: 3;
    height: 25dvh;
    margin: 5dvh;
    border-radius: 10px;
    aspect-ratio: 1/1;
    background-color: white;
    padding: 4dvh;
    padding-bottom: 3dvh;
    position: fixed;
    bottom: 0;
    right: 0;
    -webkit-box-shadow:0px 10px 45px 0px rgba(62,66,66,0.25);
    -moz-box-shadow: 0px 10px 45px 0px rgba(62,66,66,0.25);
    box-shadow: 0px 10px 45px 0px rgba(62,66,66,0.25);
    display: flex;
    flex-direction: column;
}

.hidden {
    display: none;
}

.content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    flex-grow: 1;
}

.top {
    display: flex;
    flex-direction: row;
    gap: 10px;
    align-items: center;
}

.action {
    height: 30px;
    align-self: flex-end;
    justify-self: flex-start;
    margin-top: -2dvh;
    margin-right: -2dvh;
    aspect-ratio: 1/1;
}

.illu {
    max-height: 15dvh;
    aspect-ratio: 1/1;
}

h1 {
    color: var(--medium);
    font-size: 24px;
}

button {
  background-color: #00B578;
  border: none;
  border-radius: 10px;
  padding: 15px 30px;
  font-size: 18px;
}

</style>