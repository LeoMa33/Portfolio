<template>
    <div>
        <h2>{{ props.title }}</h2>
    </div>
</template>

<script setup lang="ts">
const props = defineProps(['title'])
</script>



<style scoped>
div {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 15dvh;
}
h2 {
    color: #00B578;
    font-size: 30px;
    font-weight: bold;
}
</style>