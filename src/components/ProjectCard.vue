<template>
  <div>
    <!-- Enabled hover effects for the v-card -->
    <v-hover v-if="!mobile">
      <template v-slot:default="{ isHovering, props }">
        <!-- Adjust color and display -->
        <!-- This v-card -->
        <v-card
          v-bind="props"
          :elevation="isHovering ? 24 : 2"
          color="darker"
          dark
        >
          <!-- Adjust this div to be exactly correct -->
          <!-- Even numbered project indices show contents left aligned, while odd show more right aligned -->
          <div class="d-flex flex-no-wrap">
            <!-- An avatar shows up to the left of the content if it has an odd project index -->
            <v-avatar class="ma-3 mr-1" :size="avatarSize" rounded="0">
              <v-img
                class="project-image"
                aspect-ratio="1"
                cover
                :src="require(`../assets/${project.src}`)"
              ></v-img>
            </v-avatar>

            <!-- This div displays the title, text, and actions button -->
            <div class="py-2 d-flex flex-column justify-space-between">
              <div>
                <v-card-title class="pl-2 text-h5">
                  {{ project.title }}
                </v-card-title>

                <v-card-text class="pl-2 pb-0">
                  <div class="text--primary">
                    {{ project.description }}
                  </div>
                </v-card-text>
              </div>

              <v-card-actions v-if="project.links">
                <div
                  class="mr-5"
                  v-for="(link, index) in project.links"
                  :key="index"
                >
                  <v-btn
                    link
                    :href="link.url"
                    target="_blank"
                    variant="flat"
                    color="dark"
                  >
                    {{ link.text }}
                  </v-btn>
                </div>
              </v-card-actions>
            </div>
          </div>
        </v-card>
      </template>
    </v-hover>
    <v-card v-else>
      <!-- Adjust this div to be exactly correct -->
      <!-- Even numbered project indices show contents left aligned, while odd show more right aligned -->
      <v-img
        aspect-ratio="1"
        cover
        :src="require(`../assets/${project.src}`)"
      ></v-img>

      <v-card-title class="pl-2 text-h5">
        {{ project.title }}
      </v-card-title>

      <v-card-text class="pl-2 pb-0">
        <div class="text--primary">
          {{ project.description }}
        </div>
      </v-card-text>

      <v-card-actions v-if="project.links">
        <div class="d-flex justify-space-between flex-column">
          <div class="mt-2" v-for="(link, index) in project.links" :key="index">
            <v-btn
              link
              :href="link.url"
              target="_blank"
              variant="flat"
              color="dark"
            >
              {{ link.text }}
            </v-btn>
          </div>
        </div>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { useDisplay } from "vuetify";

export default defineComponent({
  setup() {
    const { mobile } = useDisplay();

    return { mobile };
  },
  name: "ProjectCard",
  props: {
    project: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      avatarSize: 200,
    };
  },
});
</script>

<style scoped>
.project-image {
  border-radius: 5px;
}
</style>
