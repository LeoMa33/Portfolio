<template>
    <section>
        <div class="top">
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
        </div>
        <div class="bottom">
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
            <div class="tech"></div>
        </div>
    </section>
</template>

<script setup lang="ts">

</script>



<style scoped>

section {
    margin-top: 10dvh;
    display: flex;
    flex-direction: column;
    height: 35dvh;
    gap: 2dvw;
    overflow: hidden;
}

.top {
    flex: 1;
    display: flex;
    flex-direction: row;
    gap: 2dvw;
}

.bottom {
    flex: 1;
    display: flex;
    flex-direction: row;
    margin-left: 2dvw;
    gap: 2dvw;
}

.tech {
    height: 100%;
    aspect-ratio: 1/1;
    background-color: #F2F3F7;
    border-radius: 10px;
}

</style>