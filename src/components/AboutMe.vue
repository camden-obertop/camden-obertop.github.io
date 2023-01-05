<template>
  <div>
    <div class="aboutSection">
      <div class="d-flex flex-column align-center">
        <v-avatar class="ma-3" size="300">
          <v-img :src="require(`../assets/headshot.png`)"></v-img>
        </v-avatar>
        <v-container>
          <v-row no-gutters>
            <v-col cols="10" offset="1">
              <div class="px-5 text-center">
                Hi there! My name is Camden Obertop. I currently work as a
                Junior Software Developer for Northpoint Development in Kansas
                City, Missouri. As a full stack developer I help build dynamic
                websites using primarily Vue.js. I enjoy working on video games
                made in Unity and plan on making a whole lot more of them!
              </div>
            </v-col>
          </v-row>
        </v-container>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AboutMe",
});
</script>

<style scoped>
.aboutSection {
  display: flex;
  justify-content: center;
}
</style>
