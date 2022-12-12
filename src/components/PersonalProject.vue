<template>
  <div>
    <!-- Enabled hover effects for the v-card -->
    <v-hover>
      <template v-slot:default="{ isHovering, props }">
        <!-- Adjust color and display -->
        <!-- This v-card -->
        <v-card
          v-bind="props"
          :elevation="isHovering ? 24 : 2"
          color="#385F73"
          dark
        >
          <!-- Adjust this div to be exactly correct -->
          <!-- Even numbered project indices show contents left aligned, while odd show more right aligned -->
          <div
            class="d-flex flex-no-wrap"
            :class="evenProjectIndex ? 'justify-space-between' : ''"
          >
            <!-- An avatar shows up to the left of the content if it has an odd project index -->
            <v-avatar v-if="!evenProjectIndex" class="ma-3" size="200" tile>
              <v-img :src="require(`../assets/${project.src}`)"></v-img>
            </v-avatar>

            <!-- This div displays the title, text, and actions button -->
            <div class="d-flex flex-column justify-space-between">
              <div>
                <v-card-title class="text-h5">
                  {{ project.title }}
                </v-card-title>

                <v-card-text>
                  <div class="text--primary">
                    {{ project.description }}
                  </div>
                </v-card-text>
              </div>

              <v-card-actions>
                <v-btn link :href="project.link.url" target="_blank">
                  {{ project.link.text }}
                </v-btn>
              </v-card-actions>
            </div>

            <!-- An avatar shows up to the right of the content if it has an even project index -->
            <v-avatar v-if="evenProjectIndex" class="ma-3" size="200" tile>
              <v-img :src="require(`../assets/${project.src}`)"></v-img>
            </v-avatar>
          </div>
        </v-card>
      </template>
    </v-hover>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PersonalProject",
  props: {
    project: {
      type: Object,
      required: true,
    },
    projectIndex: {
      type: Number,
      required: true,
    },
  },
  mounted() {
    console.log(this.project);
  },
  computed: {
    evenProjectIndex() {
      return this.projectIndex % 2 === 0;
    },
  },
});
</script>
