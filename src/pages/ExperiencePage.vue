<template>
    <TextualBanner title="EXPERIENCES" subtitle="RIEN DE MIEUX QUE DE L'EXPERIENCES POUR APPRENDRE"></TextualBanner>
    <div class="content">
      <ul class="experiences">
        <a href="/?exp=1" class="experience cdv">
          <h1>Cité du Vin</h1>
          <h2>Stage - Développeur FullStack</h2>
          <p>Juillet-Août 2024</p>
        </a>
      </ul>
    </div>
</template>
  
<script setup lang="ts">
  import TextualBanner from '../components/TextualBanner.vue'
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 10dvh;
}

.experiences {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  max-width: 75dvw;
  gap: 5dvw;
}

.experience {
  aspect-ratio: 1/1;
  height: 40dvh;
  padding: 30px 20px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  text-decoration: none;
}

.experience h1 {
  color: var(--primary);
  font-size: 20px;
  line-height: 20px;
}

.experience h2 {
  color: var(--light);
  font-size: 22px;
}

.experience p {
  font-weight: bold;
  color: var(--medium);
}

.cdv {
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.76)),url(/cdv.png);
  background-position: right;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>