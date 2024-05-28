<template>
    <a :href="props.link"><img :src="props.icon" alt=""><p>{{ props.text }}</p></a>
</template>

<script setup lang="ts">

const props = defineProps(['link', 'icon', 'text']);

</script>



<style scoped>
img {
    aspect-ratio: 1/1;
    width: 2dvw;
}

a {
    display: flex;
    flex-direction: row;
    align-items: center;
    text-decoration: none;
    color: white;
    gap: 5px;
    overflow: hidden;
}

a p {
    width: 0px;
}

a:hover p {
    width: auto;
}

</style>