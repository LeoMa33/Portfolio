<template>
    <SectionTitle :title="title"></SectionTitle>
    <p>Le Lorem Ipsum est simplement du faux texte employé dans la composition et la mise en page avant impression. Le Lorem Ipsum est le faux texte standard de l'imprimerie depuis les années 1500, quand un imprimeur anonyme assembla ensemble des morceaux de texte pour réaliser un livre spécimen de polices de texte. Il n'a pas fait que survivre cinq siècles, mais s'est aussi adapté à la bureautique informatique, sans que son contenu n'en soit modifié. Il a été popularisé dans les années 1960 grâce à la vente de feuilles Letraset contenant des passages du.</p>
</template>

<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
const title = "MON PARCOURT"
</script>

<style scoped>
p {
    margin-left: 12dvw;
    max-width: 50dvw;
    color: var(--medium);
    font-size: 20px;
}
</style>