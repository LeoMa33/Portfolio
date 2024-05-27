<template>
    <section>
        <SectionTitle :title="title"></SectionTitle>
        <div class="container">
            <div class="content">
                <h2>Qui suis je ?</h2>
            </div>
            <div class="content right">
                <p>Je m'appelle MACE Léo et je suis actuellement étudiant en deuxième année à Ynov Bordeaux, spécialisé en informatique. Mon intérêt pour l'informatique a commencé en 2017 lorsque j'ai débuté en autodidacte avec de petits projets personnels. Rapidement, j'ai développé une passion pour le développement d'applications mobiles, ce qui m'a amené à approfondir mes connaissances et mes compétences dans ce domaine.
Pour concrétiser cette passion, j'ai décidé d'intégrer Ynov Bordeaux, où j'ai la possibilité de développer davantage mes compétences techniques tout en bénéficiant d'un encadrement et de ressources de qualité.
En parallèle de mes études, je continue à travailler sur des projets personnels et collaboratifs, ce qui me permet de rester à jour avec les dernières technologies et tendances du secteur. Je suis toujours à la recherche de nouvelles opportunités pour apprendre et grandir dans ce domaine passionnant.</p>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
const title = "A PROPOS"
</script>

<style scoped>

section {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.container {
    display: flex;
    flex-direction: row;
    width: 60dvw;
}

.content {
    flex: 1;
}

.right {
    flex: 4;
}

h2 {
    font-weight: 500;
    color: var(--medium);
    font-size: 30px;
}

p {
    margin-left: 12dvw;
    max-width: 50dvw;
    color: var(--medium);
    font-size: 20px;
}
</style>