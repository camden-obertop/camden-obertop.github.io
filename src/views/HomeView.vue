<template>
  <div>
    <!-- Navbar -->
    <v-app-bar />
    <!-- Body -->
    <div class="siteBody">
      <!-- About Me -->
      <AboutMe />
      <!-- Links -->
      <PersonalLinks />
      <!-- Projects -->
      <PersonalProjects />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AboutMe from "../components/AboutMe.vue";
import PersonalLinks from "../components/PersonalLinks.vue";
import PersonalProjects from "../components/PersonalProjects.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    AboutMe,
    PersonalLinks,
    PersonalProjects,
  },
});
</script>

<style scoped>
.siteBody {
  margin-top: 5%;
  margin-left: 25%;
  margin-right: 25%;
}
</style>
