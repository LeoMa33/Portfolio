<template>
    <a>
        <h2>{{ props.project.title }}</h2>
        <img :src="props.project.imgPath"></img>
    </a>
</template>

<script setup lang="ts">

const props = defineProps(["project"]);

</script>

<style scoped>
a {
    display: flex;
    flex-direction: column;
    width: 30dvw;
    gap: 3dvh;
    aspect-ratio: 1/1;
}

a h2 {
    color: var(--medium);
    font-weight: 500;
}

a img {
    background-color: #F9F9F9;
    flex: 1;
    border-radius: 10px;
}
</style>