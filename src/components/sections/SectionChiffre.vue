<template>
    <section>
        <SectionTitle :title="title"></SectionTitle>
        <div class="container">
            <div class="chiffre">
                <h2>30</h2>
                <p>Projets</p>
            </div>
            <div class="chiffre">
                <h2>7</h2>
                <p>Années d'expériences</p>
            </div>
            <div class="chiffre">
                <h2>+35</h2>
                <p>Technologies</p>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
const title = "QUELQUES CHIFFRES"
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
    align-items: center;
    justify-content: center;
    width: 60dvw;
    height: 40dvh;
    gap: 10dvw;
}

.container .chiffre:nth-child(2){
    margin-bottom: 100px;
}

.chiffre {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    aspect-ratio: 1/1;
    height: 100px
}

h2 {
    font-size: 60px;
    font-weight: 400;
    color: var(--primary);
}

p {
    text-align: center;
    color: var(--medium);
}

</style>