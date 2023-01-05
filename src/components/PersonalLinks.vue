<template>
  <div class="mt-5 d-flex justify-center">
    <div class="icon-container" v-for="(link, index) in links" :key="index">
      <v-avatar size="large" rounded="0">
        <a :href="link.url" target="_blank" :title="link.title">
          <v-img
            class="link-image"
            :src="require(`../assets/${link.src}`)"
          ></v-img>
        </a>
      </v-avatar>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "PersonalLinks",
  data() {
    return {
      links: [
        {
          src: "linkIcons/linkedin.png",
          title: "LinkedIn",
          url: "https://www.linkedin.com/in/camden-obertop-b49375190/",
        },
        {
          src: "linkIcons/itchio.png",
          title: "itch.io",
          url: "https://camdeno.itch.io/",
        },
        {
          src: "linkIcons/github.png",
          title: "GitHub",
          url: "https://github.com/camden-obertop",
        },
      ],
    };
  },
});
</script>

<style scoped>
a {
  height: 100%;
  width: 100%;
}

.icon-container {
  padding-left: 25px;
  padding-right: 25px;
  padding-top: 10px;
  padding-bottom: 10px;
  background-color: #242526;
}
.icon-container:first-child {
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
}
.icon-container:last-child {
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
}
</style>
