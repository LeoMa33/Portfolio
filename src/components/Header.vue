<template>
    <nav>
        <a :class="{current:props.currentPage == 'Portfolio'}" @click="emit('changePage', 'Portfolio')">Portfolio</a>
        <a :class="{current:props.currentPage == 'Expériences'}" @click="emit('changePage', 'Expériences')">Expériences</a>
        <a :class="{current:props.currentPage == 'Réalisations'}" @click="emit('changePage', 'Réalisations')">Réalisations</a>
        <a :class="{current:props.currentPage == 'Contact'}" @click="emit('changePage', 'Contact')">Contact</a>
    </nav>
</template>

<script setup lang="ts">

const props = defineProps(['currentPage']);
const emit = defineEmits(['changePage'])

</script>



<style scoped>
nav {
    display: flex;
    flex-direction: row;
    gap: 20px;
    justify-content: center;
    align-items: center;
    height: 12.5dvh;
  }
a {
    color: var(--medium);
    text-decoration: none;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    user-select: none;
}
.current {
    color: var(--light);
}

</style>