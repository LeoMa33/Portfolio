<template>
    <section>
        <div class="top">
            <div class="tech">
                <img src="/technoIcons/logo-javascript.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/typescript.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/nodejs-1.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/vue-9.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/vitejs.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/electron-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/react-js-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/flutter-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/xamarin-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/kotlin-1.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/java.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/php-1.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/symfony-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/csharp.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/avalonia.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/cplusplus.svg" alt="">
            </div>
        </div>
        <div class="bottom">
            <div class="tech">
                <img src="/technoIcons/qt.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/python-5.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/Pandas.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/golang-1.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/html-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/css-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/sass-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/docker-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/mysql-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/firebase.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/bash.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/powershell.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/git-icon.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/ble.svg" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/mqtt-logo-ver.png" alt="">
            </div>
            <div class="tech">
                <img src="/technoIcons/nginx-1.svg" alt="">
            </div>
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
    max-height: calc(35dvh / 2 - 2dvw);
}

.bottom {
    flex: 1;
    display: flex;
    flex-direction: row;
    gap: 2dvw;
    margin-left: 2dvw;
    max-height: calc(35dvh / 2 - 2dvw);
}

.tech {
    height: 100%;
    aspect-ratio: 1/1;
    background-color: #F2F3F7;
    border-radius: 10px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

img {
    max-width: 50%;
    max-height: 50%;
}

</style>