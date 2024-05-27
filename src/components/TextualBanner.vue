<template>
    <div>
        <img src="/Untitled00180002.png" alt="">
        <h1>{{ props.title }}</h1>
        <h2>{{ props.subtitle }}</h2>
    </div>
</template>

<script setup lang="ts">

const props = defineProps(["title", "subtitle"]);

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
}

h2 {
    color: var(--primary);
    font-size: 20px;
    z-index: 2;
    text-transform: uppercase;
}
</style>