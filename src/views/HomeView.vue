<template>
  <div>
    <!-- Navbar -->
    <v-app-bar>
      <v-spacer />
      <v-btn href="#about" link> About Me </v-btn>

      <v-btn href="#projects" link> Projects </v-btn>

      <v-btn text> Resume </v-btn>
      <v-spacer />
    </v-app-bar>
    <!-- Body -->
    <div class="siteBody">
      <!-- About Me -->
      <AboutMe id="about" class="scrollTarget" />
      <!-- Links -->
      <PersonalLinks />
      <!-- Projects -->
      <PersonalProjects id="projects" class="scrollTarget" />
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
.scrollTarget {
  scroll-margin-top: 100px;
}

.navigation {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.siteBody {
  margin-top: 2%;
  margin-left: 25%;
  margin-right: 25%;
}
</style>
