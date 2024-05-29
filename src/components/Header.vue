<template>
    <nav ref="nav">
        <a :class="{current:props.currentPage == 'Portfolio'}" @click="emit('changePage', 'Portfolio')">Portfolio</a>
        <a :class="{current:props.currentPage == 'Expériences'}" @click="emit('changePage', 'Expériences')">Expériences</a>
        <a :class="{current:props.currentPage == 'Réalisations'}" @click="emit('changePage', 'Réalisations')">Réalisations</a>
        <a :class="{current:props.currentPage == 'Contact'}" @click="emit('changePage', 'Contact')">Contact</a>
        <a @click="showMenu" class="icon"><img ref="icon" :src="iconPath" alt=""></a>
    </nav>
</template>

<script setup lang="ts">

import {ref} from 'vue';


const iconPath = ref("/menu.svg")

const props = defineProps(['currentPage']);
const emit = defineEmits(['changePage'])

const showMenu = () => {
    const nav = document.querySelector('nav') as HTMLFormElement;
    if (nav.classList.contains("responsive")){
        nav.classList.remove("responsive");
        iconPath.value = "/menu.svg";
    }else {
        nav.classList.add("responsive");
        iconPath.value = "/fermerwhite.png";
    }
}

</script>



<style scoped>
nav {
    position: absolute;
    z-index: 4;
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

a.icon {
    display: none;
    height: 50px;
    aspect-ratio: 1/1;
}

a.icon img {
    width: 100%;
}


@media (max-width: 600px) {
    nav{
        align-items: flex-end;
        flex-direction: column;
        min-height: 10dvh;
        height: auto;
    }
    nav a {
        display: none;
    }
    nav a.icon {
        float: right;
        display: block;
        margin-right: 20px;
        margin-top: 2dvh;
    }

    nav.responsive {
        height: 100dvh;
        background-color: rgba(0, 0, 0, 0.74);
        justify-content: center;
        align-items: center;
    }

    nav.responsive a {
        float: none;
        display: block;
        text-align: left;
        margin-right: 20px;
        font-size: 24px;
    }
}

/*@media (max-width: 600px) {
  .topnav.responsive {position: relative;}
  .topnav.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}*/

</style>