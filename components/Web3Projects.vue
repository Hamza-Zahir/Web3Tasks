<template>
  <div class="container mb-5 pb-5">
    <div class="mt-5 mx-auto">
      <h5 class="m-3"><span class="advanced mr-2"></span>Advanced Projects</h5>
      <div class="text-center content m-0 p-0">
        <div class="tabel d-flex  m-0 p-0 bg-secondary text-light">
          <span class="col-1 border  border-dark py-1">#</span>
          <span class="col border  border-dark py-2">Projects Name</span>
          <span class="col border  border-dark py-2">Original Projects</span>
          <span class="col border  border-dark py-2">My Results</span>
          <span class="col-2 border  border-dark py-2">Done</span>
        </div>
        <div class="tabel" v-for="project in AllProjects" :key="project.id">
          <div class="d-flex m-0 p-0" :class="project.advanced ? 'advanced':'bg-blue'">
            <span class="col-1 border  border-dark py-2">{{ project.id }}</span>
            <span class="col border  border-dark py-2">{{ project.title }}</span>
            <span
              class="col border border-dark py-2 d-flex flex-nowrap justify-content-around"
            >
              <a
                class=""
                v-if="project.OriginalProjects.tutorial"
                :href="project.OriginalProjects.tutorial"
                target="blank"
              >
                {{
                  project.OriginalProjects.sourceCode
                    ? "Tutorial"
                    : "Tutorial And Code"
                }}
              </a>
              <div v-if="project.OriginalProjects.sourceCode">/</div>
              <a
                class=""
                v-if="project.OriginalProjects.sourceCode"
                :href="project.OriginalProjects.sourceCode"
                target="blank"
              >
                Source Code
              </a>
            </span>
            <span
              class="col border  border-dark py-2 d-flex flex-nowrap m-0 justify-content-around"
              ><a class="" :href="project.myResults.sourceGithub" target="blank">
                Github Source
              </a>
             /
              <a :href="project.myResults.websit" target="blank"> website </a></span
            >
            <span class="col-2 border  border-dark py-2">
              {{ project.done ? "Done" : "under construction" }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import AllProjects from "~/json/Web3Projects.json";
export default {
  data() {
    return {
      AllProjects,
    };
  },

};
</script>
<style>
 .content{
  overflow: scroll;
}
.content::-webkit-scrollbar {
    width: 0px;
    height: 2px;
  }
  .content::-webkit-scrollbar-track {
    background: rgb(249, 255, 255);
  }

.tabel{
  min-width: 800px;

}
body{
  background: #e9e9e9;
}
.bg-blue {
  background: rgb(229, 230, 238);
}
</style>
