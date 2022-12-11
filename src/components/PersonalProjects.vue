<template>
  <div>
    <div>Personal Projects</div>
    <div>
      <PersonalProject
        v-for="(project, index) in projects"
        :key="index"
        :project="project"
        :projectIndex="index"
        class="projectDisplay"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import PersonalProject from "./PersonalProject.vue";

export default defineComponent({
  name: "PersonalProjects",
  components: {
    PersonalProject,
  },
  data() {
    return {
      projects: [
        {
          title: "Orthogonia",
          description:
            "Orthogonia is a virtual reality game where you solve three dimension 'picross' puzzles to restore the natural world in a desolate wasteland",
          src: "tree.png",
          link: {
            text: "Watch Gameplay",
            url: "https://www.youtube.com/watch?v=FFX8VtoFeb8",
          },
        },
        {
          title: "Neural Nest",
          description: "Neural Nest is a game where you are neural in a nest",
          src: "mario_real.png",
          link: {
            text: "Watch Gameplay",
            url: "https://www.youtube.com/watch?v=Ka-yAR-SoiY",
          },
        },
      ],
    };
  },
});
</script>

<style scoped>
.projectDisplay:not(:first-of-type) {
  margin-top: 3em;
}
</style>
