<template>
    <section>
        <div class="container">
            <h2>SoftSkills</h2>
            <div class="content">
                <ul class="part">
                    <li class="select"><h3>Title</h3></li>
                    <li><h3>Title</h3></li>
                    <li><h3>Title</h3></li>
                </ul>
                <div class="part desc">
                    <h3>Title</h3>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. In, possimus? Expedita quidem, aspernatur cupiditate a voluptas id molestiae tempore odio error, exercitationem iusto sint dolorem! Voluptatibus magni consectetur et consequatur!</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">

</script>

<style scoped>

section {
    margin-top: 10dvh;
    margin-bottom: 5dvh;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.container {
    padding: 40px;
    width: calc(60dvw - 80px);
    display: flex;
    align-items: center;
    flex-direction: column;
    aspect-ratio: 16/6.92;
    border-radius: 10px;
    background-color: #00b5790e;
    gap: 10px;
}

h2 {
    font-weight: 400;
    color: var(--primary);
    font-size: 30px;
}

.content {
    flex: 1;
    width: 100%;
    display: flex;
    flex-direction: row;
}

.part {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

ul {
    gap: 10px;
    align-items: center;
    margin: 25px;
}

li {
    width: 80%;
    color: var(--primary);
    padding: 25px 25px;
    border-radius: 10px;
    display: flex;
    flex-direction: row;
    align-items: center;
}

.select {
    background-color: var(--primary);
    color: white;
}

.desc {
    gap: 10px;
    margin: 10px;
}

.desc h3 {
    color: var(--primary);
    font-size: 25px;
    font-weight: 400;
}

.desc p {
    font-size: 20px;
    color: var(--medium);
}

</style>