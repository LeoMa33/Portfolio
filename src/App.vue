

<template>
  <div class="container">
    <Header :current-page="currentPage" @change-page="changePage"></Header>
    <HomePage v-if="currentPage == 'Portfolio'"/>
    <ExperiencePage v-if="currentPage == 'Expériences'"/>
    <ArticlePage v-if="currentPage == 'Article'"></ArticlePage>
    <EntreprisePage v-if="currentPage == 'Entreprise'"></EntreprisePage>
    <RealisationPage v-if="currentPage == 'Réalisations'"/>
    <ContactPage v-if="currentPage == 'Contact'"/>
    <div style="height: 10dvh;"></div>
    <Footer></Footer>
  </div>
</template>

<script setup lang="ts">
import Header from './components/Header.vue'
import Footer from './components/Footer.vue';
import ArticlePage from './pages/ArticlePage.vue';
import HomePage from './pages/HomePage.vue'
import RealisationPage from './pages/RealisationPage.vue';
import ExperiencePage from './pages/ExperiencePage.vue';
import ContactPage from './pages/ContactPage.vue';
import EntreprisePage from './pages/EntreprisePage.vue';

import {ref} from 'vue';

let url = new URL(window.location.href);
let exp = url.searchParams.get("exp");
let art = url.searchParams.get("art");


const currentPage = ref("Portfolio");

if (exp) {
  currentPage.value = "Entreprise";
}else if (art){
  currentPage.value = "Article";
}

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
