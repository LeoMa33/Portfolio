<template>
    <div>
        <img :src="image" alt="" :class="{ cover : props.image }">
        <h1>{{ props.title }}</h1>
        <h2>{{ props.subtitle }}</h2>
    </div>
</template>

<script setup lang="ts">

const props = defineProps(["title", "subtitle", "image"]);

const image = props.image ? props.image : "/Untitled00180002.png"

</script>



<style scoped>
div {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 61dvh;
    background-color: #1F1F29;
    overflow: hidden;
}

img {
    position: absolute;
    z-index: 1;
    filter: blur(4px) opacity(10%);
    opacity: 90%;
    bottom: 0;
}

h1 {
    color:  var(--light);
    font-size: 60px;
    z-index: 2;
    max-width: 90dvw;
    text-align: center;
    text-transform: uppercase;
}

h2 {
    color: var(--primary);
    font-size: 20px;
    z-index: 2;
    text-transform: uppercase;
    text-align: center;
    max-width: 90dvw;
}

.cover {
    width: 100dvw;
    top: 0;
}

</style>