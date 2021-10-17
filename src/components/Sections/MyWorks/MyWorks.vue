<template>
  <div class="my-works">
    <h1 style="" class="text-lg-h2 font-weight-bold mt-8">My Works</h1>
    <div class="flex-container">
      <div class="project-flex">
        <ProjectDialog
            v-for="(project, index) in workData.projects"
            :project="project"
            :key="index"

        ></ProjectDialog>
      </div>
    </div>
  </div>
</template>

<script>
import ProjectDialog from "@/components/Sections/MyWorks/ProjectDialog";
import workJson from "@/data/my_works.json";

export default {
  name: "MyWorks",
  components: {ProjectDialog},
  data() {
    return {
      workData: workJson,
    }
  }
}
</script>

<style scoped>
h1 {
  position: relative;
  z-index: 1;
  color: #202040;
  margin-left: 10%;
}

h1:after {
  content: "";
  position: absolute;
  width: 10vw;
  height: 30px;
  background-color: #FF1E56;
  left: 0px;
  bottom: 0px;
  z-index: -1;
}

.my-works {
  width: 100%;
  height: 100vh;
  background-color: white;
}

.flex-container {
  width: 100%;
  display: flex;
  padding: 0;
  margin: 0;
  align-items: center;
  justify-content: center;
}

.project-flex {
  display: flex;
  flex-direction: row;
  align-items: stretch;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 30px;
  max-width: 1500px;
}
</style>
