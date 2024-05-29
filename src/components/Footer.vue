<template>
    <div class="footer">

        <ul class="link">
            <li><IconTexteHover link="https://github.com/LeoMa33" icon="/icons/github.svg" text="LeoMa33"></IconTexteHover></li>
            <li><IconTexteHover link="https://www.linkedin.com/in/léo-mace-142234266/" icon="/icons/linkedin.svg" text="Léo MACE"></IconTexteHover></li>
            <li><IconTexteHover link="mailto:mace.leo33@gmail.com" icon="/icons/mail.svg" text="mace.leo33@gmail.com"></IconTexteHover></li>
            <li><IconTexteHover link="tel:0682546806" icon="/icons/phone.png" text="06.82.54.68.06"></IconTexteHover></li>
        </ul>

        <p>@Copyright, Tous droits réservés</p>
        <p>Développé par MACE Léo</p>
    </div>
</template>

<script setup lang="ts">

import IconTexteHover from './IconTexteHover.vue'

</script>



<style scoped>
.footer {
    background-color: #1F1F29;
    height: 25dvh;
    padding: 2dvh;
    display: flex;
    flex-direction: column;
    justify-content: end;
    align-items: center;
}

.link {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 2dvw;
    flex-grow: 1;
}

.footer p {
    color: var(--light);
}

</style>