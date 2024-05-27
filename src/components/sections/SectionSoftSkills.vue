<template>
    <section>
        <div class="container">
            <h2>SoftSkills</h2>
            <div class="content">
                <ul class="part">
                    <li :class="{select:currentSkill==idx}" v-for="sk, idx in softskills" v-on:click="currentSkill = idx"><h3>{{ sk.title }}</h3></li>
                </ul>
                <div class="part desc">
                    <h3>{{ softskills[currentSkill].title }}</h3>
                    <p>{{ softskills[currentSkill].desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">


import {ref} from 'vue';

const currentSkill = ref(0);

const softskills:SoftSkillsType[] = [
    {title:"Autodidact", desc:"Je suis autodidacte avec une soif d'apprendre et une grande curiosité. C'est cette curiosité qui m'a conduit à la programmation. J'ai appris par moi-même, explorant différents langages et technologies, et développant des compétences en résolution de problèmes de manière indépendante et créative. Mon parcours reflète mon engagement envers l'apprentissage continu et ma passion pour la découverte."},
    {title:"Créatif", desc:"Je suis une personne créative, capable de voir les choses sous différents angles et de trouver des solutions innovantes. Dans la programmation et d'autres domaines, j'aime expérimenter et sortir des sentiers battus. Cela me permet de proposer des solutions originales et d'apporter une touche personnelle à mes projets."},
    {title:"Adaptivité", desc:"Je suis très adaptable et capable de m'ajuster rapidement à de nouvelles situations. Que ce soit dans la programmation ou dans d'autres domaines, j'apprends vite et m'adapte aux changements avec aisance. Cette flexibilité me permet de relever des défis variés et de toujours trouver des solutions appropriées aux problèmes rencontrés."}
]


</script>

<style scoped>

section {
    margin-top: 10dvh;
    margin-bottom: 5dvh;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.container {
    padding: 40px;
    width: calc(60dvw - 80px);
    display: flex;
    align-items: center;
    flex-direction: column;
    aspect-ratio: 16/6.92;
    border-radius: 10px;
    background-color: #00b5790e;
    gap: 10px;
}

h2 {
    font-weight: 400;
    color: var(--primary);
    font-size: 30px;
}

.content {
    flex: 1;
    width: 100%;
    display: flex;
    flex-direction: row;
}

.part {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

ul {
    gap: 10px;
    align-items: center;
    margin: 25px;
}

li {
    width: 80%;
    color: var(--primary);
    padding: 25px 25px;
    border-radius: 10px;
    display: flex;
    flex-direction: row;
    align-items: center;
    cursor: pointer;
}

.select {
    background-color: var(--primary);
    color: white;
}

.desc {
    gap: 10px;
    margin: 10px;
}

.desc h3 {
    color: var(--primary);
    font-size: 25px;
    font-weight: 400;
}

.desc p {
    font-size: 20px;
    color: var(--medium);
}

</style>