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
    
    position: absolute;
    z-index: 2;
    display: flex;
    flex-direction: row;
    gap: 20px;
    justify-content: center;
    align-items: center;
    height: 10dvh;
    width: 100%;
  }
a {
    color: var(--medium);
    color: var(--light);
    text-decoration: none;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    user-select: none;
}
.current {
    color: var(--primary);
}

</style>