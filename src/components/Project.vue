<template>
    <a>
        <h2>{{ props.project.title }}</h2>
        <ul>
            <li v-for="tech in props.project.technologie">
                {{ tech }}
            </li>
        </ul>
        <div class="container">
            <img :src="props.project.imgPath"></img>
            
            <div class="hoverdetect"></div>
            <div class="desc">
                <h2>{{ props.project.domaine }}</h2>
                <p>{{ props.project.shortDescription }}</p>
            </div>
        </div>
    </a>
</template>

<script setup lang="ts">

const props = defineProps(["project"]);

</script>

<style scoped>
a {
    display: flex;
    flex-direction: column;
    width: 30dvw;
    gap: 10px;
    aspect-ratio: 1/1;
}

a h2 {
    color: var(--medium);
    font-weight: 500;
}

a .container {
    position: relative;
    min-width: 300px;
    min-height: 300px;
    flex: 1;
    aspect-ratio: 1/1;
}

a .container .desc {
    background: linear-gradient(0deg, rgb(26, 26, 26), rgba(26,26,26,0.4) , rgba(26, 26, 26, 0.08));
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    overflow: hidden;
    height: 0%;
    width: 100%;
    bottom: 0;
    left: 0;
    border-radius: 10px;
    transition: all ease-out 500ms;
    z-index: 1;
}

a .container img {
    height: 100%;
    width: 100%;
    border-radius: 10px;
}

.hoverdetect {
    position: absolute;
    height: 100%;
    width: 100%;
    z-index: 2;
    bottom: 0;
    left: 0;
}

.hoverdetect:hover + .desc{
    height: 100%;
}

a .container .desc h2 {
    margin: 0% 5%;
    font-weight: 700;
    font-size: 18px;
    color: #00b579;
}

a .container .desc p {
    margin: 0% 5% 5% 5%;
    color: white;
    min-height: 15%;
}

ul {
  display: flex;
  flex-direction: row;
  gap: 10px;
  flex-wrap: wrap;
}

li {
    background-color: #00b57949;
    padding: 2px 15px;
    border-radius: 5px;
    font-weight: bold;
    color: white;
}
</style>