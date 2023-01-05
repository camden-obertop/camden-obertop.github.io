<template>
  <div class="mt-5">
    <div class="text-h3 text-center pb-3">{{ sectionName }}</div>
    <div>
      <ProjectCard
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
import ProjectCard from "./ProjectCard.vue";

export default defineComponent({
  name: "ProjectList",
  components: {
    ProjectCard,
  },
  props: {
    sectionName: {
      type: String,
      required: true,
    },
    projects: {
      type: Array,
      required: true,
    },
  },
});
</script>

<style scoped>
.projectDisplay:not(:first-of-type) {
  margin-top: 3em;
}
</style>
