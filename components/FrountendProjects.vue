<template>
  <div class="container">
    <div class="mt-5 mx-auto">
      <h5 class="m-3"><span class="advanced mr-2"></span>Advanced Projects</h5>

      <div class="text-center content">

        <div class="tabel d-flex m-0 p-0 bg-secondary text-light">
          <span class="col-1 border border-dark py-1">#</span>
          <span class="col border border-dark py-2">Projects Name</span>
          <span class="col border border-dark py-2">Github Source</span>
          <span class="col border border-dark py-2">website</span>
          <span class="col-2 border border-dark py-2">Done</span>
        </div>

        <div class="" v-for="project in AllProjects" :key="project.id">
          <div class="d-flex m-0 p-0  tabel " :class="project.advanced ? 'advanced':'bg-blue'">
            <span class="col-1 border border-dark py-2">{{ project.id }}</span>
            <span class="col border border-dark py-2">{{ project.projectName }}</span>
            <span
              class="col border border-dark py-2"
            >
              <a
                class=""
                :href="project.sourceGithub"
                target="blank"
              >
                {{ project.sourceGithub }}
              </a>
            </span>
            <span
              class="col border border-dark py-2"
            >
              <a
                class=""
                :href="project.websit"
                target="blank"
              >
                {{ project.websit }}
              </a>
            </span>

            <span class="col-2 border border-dark py-2">
              {{ project.done ? "Done" : "under construction" }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import AllProjects from "~/json/FrontendProjects.json";
export default {
  data() {
    return {
      AllProjects,
    };
  },

};
</script>
<style>
   a {
      overflow: hidden;
      display: -webkit-box;
      display: -moz-box;
      -webkit-box-orient: vertical;
      -moz-box-orient: vertical;
      text-overflow: ellipsis;
      -webkit-line-clamp: 1;
      line-clamp: 1;
      /* font-size: 14px; */
    }
 .content{
  overflow: scroll;
}
.content::-webkit-scrollbar {
    width: 0px;
    height: 2px;
  }
  .content::-webkit-scrollbar-track {
    background: #f9ffff;
  }

.tabel{
  min-width: 800px;

}
.bg-blue {
  background: #e5e6ee;
}
.advanced{
  background: #50c9f8;
}
h5 span{
  display: inline-block;
  width: 20px;
  height: 20px;

}
</style>
