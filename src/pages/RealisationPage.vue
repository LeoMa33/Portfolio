<template>
  <div class="content">
    <div class="left">
      <Project v-for="prj in getIsDivideIndexProjects(projects,0)" :project="prj"/>
    </div>
    <div class="right">
      <Project v-for="prj in getIsDivideIndexProjects(projects,1)" :project="prj"/>
    </div>
  </div>
</template>

<script setup lang="ts">
//import { ref } from 'vue';
import Project from '../components/Project.vue'

/*const project = ref<ProjectType>({
  title:"test"
})*/

const getIsDivideIndexProjects = (projects:ProjectType[], divideResult:number)=>{
  return projects.filter((_,idx) => idx%2==divideResult);
};

const projects:ProjectType[] = [{
  title:"Easfert",
  imgPath:"/projects/Easfert.png",
  domaine:"Application Mobile",
  technologie:["Xamarin", "Bluetooth Low Energie"],
  shortDescription:"Application de transfert de données via Bluetooth Low Energy.",
},{
  title:"Inventory Manager",
  imgPath:"/projects/InventoryManager.png",
  domaine:"Application Mobile",
  technologie:["React Native"],
  shortDescription:"Application de gestion de stock pouvant scanner des codes bar afin d'identifier un article.",
},{
  title:"Xamarin GridView",
  imgPath:"/projects/GridView.png",
  domaine:"Composant",
  technologie:["Xamarin", "Composant"],
  shortDescription:"Composant Xamarin permettant l'organisation d'éléments en grille.",
}]

</script>

<style scoped>

.content {
  display: flex;
  flex-direction: row;
  gap: 8dvh;
  justify-content: center;
  width: 100dvw;
}

.left{
  display: flex;
  flex-direction: column;
  gap: 8dvh;
}
.right{
  display: flex;
  flex-direction: column;
  margin-top: 10dvh;
  gap: 8dvh;
}

</style>