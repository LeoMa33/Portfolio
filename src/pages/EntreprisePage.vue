<template>
    <TextualBanner image="/cdv.png" :title="entreprise[Number(exp)-1].title" subtitle="STAGE - Développeur FullStack"></TextualBanner>
    <section>
        <SectionTitle title="A PROPOS"></SectionTitle>
        <div class="container">
            <div class="content right">
                <p>{{ entreprise[Number(exp)-1].desc }}</p>
            </div>
        </div>
    </section>
    <SectionTitle title="ARTICLES"></SectionTitle>
    <ul class="articles">
      <a :href="'/?art='+article.id" v-for="article in entreprise[Number(exp)-1].articles" class="article">
        <h2 class="articleTitle">{{ article.title }}</h2>
        <p class="articleDate">{{ article.date }}</p>
      </a>
    </ul>
</template>
  
<script setup lang="ts">
  import SectionTitle from '../components/sections/SectionTitle.vue';
  import TextualBanner from '../components/TextualBanner.vue'
  
  let url = new URL(window.location.href);
  let exp = url.searchParams.get("exp");

  const entreprise = [
    {
      title:"Cité du Vin",
      articles:[{
        id:1,
        title:"Arrivé à la Cité du Vin",
        date:"17 Juin 2024",
      },{
        id:2,
        title:"Analyse et prototypage du « Jeu des Couleurs »",
        date:"21 Juin 2024",
      },{
        id:3,
        title:"Un nouveau sujet de stage",
        date:"28 Juin 2024",
      },{
        id:4,
        title:"« Jeu des Couleurs, du prototype au fonctionnel »",
        date:"2 Août 2024",
      },{
        id:5,
        title:"Conclusion",
        date:"9 Août 2024",
      }],
      desc:"La Cité du Vin, située à Bordeaux, est un lieu emblématique dédié à la culture et à l'histoire du vin. Conçue comme un véritable voyage sensoriel, elle se distingue par son architecture audacieuse, inspirée par les mouvements du vin dans un verre et les courbes naturelles de la vigne. Le bâtiment, avec ses formes arrondies et sa façade dorée qui capte la lumière, se dresse majestueusement au bord de la Garonne, ajoutant une touche contemporaine au paysage bordelais. À l'intérieur, la Cité du Vin propose un parcours immersif où les visiteurs peuvent explorer l'histoire du vin à travers les âges et les cultures. L'exposition permanente est interactive, mêlant technologies numériques, vidéos, et installations artistiques pour offrir une expérience captivante. Chaque espace est conçu pour éveiller les sens : on peut sentir les arômes des vins, toucher les matériaux liés à la viticulture, et bien sûr, déguster des vins du monde entier. En plus de l'exposition permanente, la Cité du Vin accueille des expositions temporaires, des conférences, et des ateliers de dégustation. Le belvédère, situé au 8ème étage, offre une vue panoramique sur Bordeaux et ses vignobles environnants, invitant les visiteurs à contempler l'influence du vin sur la région."
    }
  ]




</script>

<style scoped>

section {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.articles {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  padding: 0 10dvw;
  align-items: center;
  justify-content: center;
  gap: 5dvh;
}

.article {
  text-decoration: none;
  background-color: black;
  aspect-ratio: 1/1;
  height: 30dvh;
  border-radius: 10px;
  padding: 25px;
  display: flex;
  flex-direction: column;
  justify-content: end;
}

.articleTitle {
  color: var(--primary);
  text-wrap: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-width: 85%;
  font-size: 24px;
}

.articleDate {
  font-size: 18px;
  width: 100%;
  font-weight: bold;
  color: var(--light);
  margin: 0;
}

.container {
    display: flex;
    flex-direction: row;
    width: 75dvw;
    flex-wrap: wrap;
}

.right {
    min-width: 75dvw;
}

h2 {
    font-weight: 500;
    color: var(--medium);
    font-size: 30px;
    min-width: 165px;
}

p {
    max-width: 70dvw;
    margin-top: 20px;
    color: var(--medium);
    font-size: 20px;
}

@media (min-width: 1350px){

    p {
        margin-left: 12dvw;
        margin-top: 0px;
        max-width: 50dvw;
        color: var(--medium);
        font-size: 20px;
    }

}
</style>