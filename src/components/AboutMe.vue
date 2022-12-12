<template>
  <div>
    <div class="text-h5 text-center">About Me</div>
    <div class="aboutSection">
      <div>
        <v-avatar class="ma-3" size="500" tile>
          <v-img :src="require(`../assets/mario_real.png`)"></v-img>
        </v-avatar>
        <div class="text-center">It's a me</div>
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
