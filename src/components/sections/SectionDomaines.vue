<template>
    <SectionTitle :title="title"></SectionTitle>
    <div class="list">
        <div class="domaine">
            <div class="illu">
                <img src="/ordinateur-portable.png" alt="" srcset="">
            </div>
            <div class="info">
                <h1>Développement Logiciel</h1>
                <!--<p>desc</p>-->
            </div>
        </div>
        <div class="domaine">
            <div class="illu">
                <img src="/developpement-mobile.png" alt="" srcset="">
            </div>
            <div class="info">
                <h1>Développement Mobile</h1>
                <!--<p>desc</p>-->
            </div>
        </div>
        <div class="domaine">
            <div class="illu">
                <img src="/iot.png" alt="" srcset="">
            </div>
            <div class="info">
                <h1>Développement IOT</h1>
                <!--<p>desc</p>-->
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import SectionTitle from './SectionTitle.vue'
const title = "MES DOMAINES"
</script>

<style scoped>
.list {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 5dvw;
}
.domaine {
    display: flex;
    flex-direction: column;
    background-color: #00b5790e;
    aspect-ratio: 3/4;
    width: 12dvw;
    min-width: 200px;
    align-items: center;
    padding: 20px;
    border-radius: 20px;
    justify-content: space-between;
}

img {
    aspect-ratio: 1/1;
    width: 50%;
}

.illu {
    flex: 1.5;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.info {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
}

h1 {
    font-size: 22px;
    max-width: 80%;
    text-align: center;
    color: var(--medium);
}

p {
    color: var(--medium);
    font-size: 20px;
}
</style>