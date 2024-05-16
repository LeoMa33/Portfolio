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
  imgPath:"/Frame10.png",
  domaine:"Application Mobile"
},{
  title:"Unknown",
  imgPath:"none",
  domaine:""
},{
  title:"Unknown",
  imgPath:"none",
  domaine:""
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

a {
  display: flex;
  flex-direction: column;
  width: 30dvw;
  gap: 3dvh;
  aspect-ratio: 1/1;
}

a h2 {
  color: var(--medium);
  font-weight: 500;
}

a img {
  background-color: #F9F9F9;
  flex: 1;
  border-radius: 10px;
}
</style>