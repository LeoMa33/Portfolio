

<template>
  <div class="container">
    <Header :current-page="currentPage" @change-page="changePage"></Header>
    <HomePage v-if="currentPage == 'Portfolio'"/>
    <ExperiencePage v-if="currentPage == 'Expériences'"/>
    <RealisationPage v-if="currentPage == 'Réalisations'"/>
    <ContactPage v-if="currentPage == 'Contact'"/>
    <div style="height: 10dvh;"></div>
    <Footer></Footer>
  </div>
</template>

<script setup lang="ts">
import Header from './components/Header.vue'
import Footer from './components/Footer.vue';
import HomePage from './pages/HomePage.vue'
import RealisationPage from './pages/RealisationPage.vue';
import ExperiencePage from './pages/ExperiencePage.vue';
import ContactPage from './pages/ContactPage.vue';

import {ref} from 'vue';

const currentPage = ref("Portfolio");
const changePage = (page:any)=>{
  currentPage.value = page
}


</script>

<style scoped>

.container {
  width: 100%;
  overflow-x: hidden;
}

</style>
