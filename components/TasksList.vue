<template>
  <div class="abb">
    <h2 class="bg-dark text-center text-light py-3">List Of Web3 projects</h2>

    <div class="mt-5 mx-auto col-lg-10 col-xl-9">
      <div class="text-center content">
        <div class="tabel d-flex m-0 p-0 bg-secondary text-light">
          <span class="col-1 border py-1">#</span>
          <span class="col border py-2">Projects Name</span>
          <span class="col border py-2">Original Projects</span>
          <span class="col border py-2">My Results</span>
          <span class="col-2 border py-2">Done</span>
        </div>
        <div class="tabel" v-for="task in AllTasks" :key="task.id">
          <div class="d-flex m-0 p-0 bg-blue">
            <span class="col-1 border py-2">{{ task.id }}</span>
            <span class="col border py-2">{{ task.title }}</span>
            <span
              class="col border py-2 d-flex flex-nowrap justify-content-around"
            >
              <a
                class="border-right"
                v-if="task.OriginalProjects.tutorial"
                :href="task.OriginalProjects.tutorial"
                target="blank"
              >
                {{
                  task.OriginalProjects.sourceCode
                    ? "Tutorial"
                    : "Tutorial And Code"
                }}
              </a>
              <div v-if="task.OriginalProjects.sourceCode">/</div>
              <a
                class=""
                v-if="task.OriginalProjects.sourceCode"
                :href="task.OriginalProjects.sourceCode"
                target="blank"
              >
                Source Code
              </a>
            </span>
            <span
              class="col border py-2 d-flex flex-nowrap m-0 justify-content-around"
              ><a class="border-right" :href="task.myResults.sourceGithub" target="blank">
                Github Source
              </a>
             /
              <a :href="task.myResults.websit" target="blank"> websit </a></span
            >
            <span class="col-2 border py-2">
              {{ task.done ? "Done" : "under construction" }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import AllTasks from "../json/allTasks.json";
export default {
  data() {
    return {
      AllTasks,
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
  background: rgb(109, 109, 109);
}
.bg-blue {
  background: rgb(229, 230, 238);
}
</style>
