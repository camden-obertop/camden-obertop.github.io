<template>
  <div>
    <div class="aboutSection">
      <div class="d-flex flex-column align-center">
        <v-avatar class="ma-3" size="300">
          <v-img :src="require(`../assets/headshot.png`)"></v-img>
        </v-avatar>
        <div class="px-5 text-center">
          Hi there! My name is Camden Obertop. I currently work as a Junior
          Software Developer for Northpoint Development in Kansas City,
          Missouri.
        </div>
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
