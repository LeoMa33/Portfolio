<template>
    <nav>
        <a :class="{current:currentPage == 'Portfolio'}" v-on:click="currentPage='Portfolio'">Portfolio</a>
        <a :class="{current:currentPage == 'Expériences'}" v-on:click="currentPage='Expériences'">Expériences</a>
        <a :class="{current:currentPage == 'Réalisations'}" v-on:click="currentPage='Réalisations'">Réalisations</a>
        <a :class="{current:currentPage == 'Contact'}" v-on:click="currentPage='Contact'">Contact</a>
    </nav>
</template>

<script setup lang="ts">

import {ref} from 'vue';

const currentPage = ref("Portfolio");

</script>



<style scoped>
nav {
    display: flex;
    flex-direction: row;
    gap: 20px;
    justify-content: center;
    align-items: center;
    height: 12.5dvh;
  }
a {
    color: #737373;
    text-decoration: none;
    font-size: 18px;
    font-weight: bold;
}
.current {
    color: #C9C9C9;
}

</style>