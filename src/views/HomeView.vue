<template>
  <div class="home-container">
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
      <!-- Big Projects -->
      <ProjectList
        id="projects"
        class="scrollTarget projectList"
        section-name="Personal Projects"
        :projects="ongoingProjects"
      />
      <!-- Game Jams and Hackathon Projects -->
      <ProjectList
        class="projectList"
        section-name="Hackathon and Game Jam Projects"
        :projects="jamProjects"
      />
      <!-- Game Jams and Hackathon Projects -->
      <ProjectList
        class="projectList"
        section-name="School Projects"
        :projects="schoolProjects"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AboutMe from "../components/AboutMe.vue";
import PersonalLinks from "../components/PersonalLinks.vue";
import ProjectList from "../components/ProjectList.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    AboutMe,
    PersonalLinks,
    ProjectList,
  },
  data() {
    return {
      ongoingProjects: [
        {
          title: "Neural Nest",
          description:
            "Neural Nest is a game made in Unity that I have worked on with my team at Q-Bit Digital LLC.\
            It is a surreal first person shooter where you journey through a concrete megastructure.\
            We started working on this game as the entrepreneurial senior design project at the University of Nebraska-Lincoln.\
            For this game, my main responsibilities have included creating concept art and designing levels.\
            For designing levels, I've worked with the Unity packages UModeler and ProBuilder.\
            We are working hard to release a demo in early 2023.",
          src: "projectImages/neural_nest.png",
          links: [
            {
              text: "Watch Gameplay",
              url: "https://www.youtube.com/watch?v=UbQon-5eEJ4",
            },
          ],
        },
        {
          title: "Orthogonia",
          description:
            "Orthogonia is a virtual reality game made in Unity that I worked on with Jaden Goter and Gabe Eubanks.\
            In Orthogonia, you solve 3D 'picross' style puzzles to restore a desolate wasteland.\
            This project was created for a special topics virtual reality course at the University of Nebraska-Lincoln.\
            The game was created using Unity and I worked as a gameplay programmer.\
            We are considering polishing the game and releasing it for free on Steam.",
          src: "projectImages/orthogonia.png",
          links: [
            {
              text: "Watch Gameplay",
              url: "https://www.youtube.com/watch?v=FFX8VtoFeb8",
            },
          ],
        },
        {
          title: "Slime Slide",
          description:
            "Slime Slide is a mobile game where you play as a ball of slime rolling down an infinite tube.\
            The game was created in Unity. I worked on game design and programming.\
            I worked on this game with my friends Jaden Goter, Matt Lowe, and Erik Skoog.\
            The game is available on both the Google Play Store and the Apple App Store.",
          src: "projectImages/slime_slide.png",
          links: [
            {
              text: "View on Google Play Store",
              url: "https://play.google.com/store/apps/details?id=com.QBitDigitalLLC.SlimeSlideGame&hl=en_US&gl=US",
            },
            {
              text: "View on Apple App Store",
              url: "https://apps.apple.com/au/app/slime-slide/id1616745693",
            },
          ],
        },
        {
          title: "Encryptid",
          description:
            "Encrypted is a 2D platformer where you play as a few cryptid characters in a facility, trying to escape.\
            The game started as a submission to the Univeristy of Nebraska-Lincoln's Cornhacks hackathon in 2020.\
            After Cornhacks, we continued development to make it a full 30 minute game.\
            I worked on this game with Jaden Goter, Grant Davis, and Matt Lowe.\
            I worked on the sprite art for this game.",
          src: "projectImages/encryptid.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://jadengoter.itch.io/encryptid",
            },
            {
              text: "Play on Newgrounds",
              url: "https://www.newgrounds.com/portal/view/775951",
            },
          ],
        },
        {
          title: "camdenobertop.com",
          description:
            "I made this website using Vue and Vuetify.\
            I wanted this website to a gallery of all the projects I've worked on in one convenient place.",
          src: "headshot.png",
        },
      ],
      jamProjects: [
        {
          title: "Critter Casino",
          description:
            "Critter Casino is a 2D tower defense game made in Unity.\
            It was a submission for the GMTK Game Jam 2022, which took place in July of 2022.\
            The game received 275th place overall out of 6,112 entries.\
            I worked primarily on game design and sprite art.",
          src: "projectImages/critter_casino.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://camdeno.itch.io/critter-casino",
            },
          ],
        },
        {
          title: "Weevil Warrior",
          description:
            "Weevil Warrior is a 2D platformer created for Game Boy using the ZGB game engine.\
            This game was a submission for the University of Nebraska-Lincoln's retro-themed Cornhacks 2022, where we received 2nd place.\
            I worked on this game with my friends Jaden Goter and Erik Skoog.\
            I worked on level design and sprite art.",
          src: "projectImages/weevil_warrior.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://jadengoter.itch.io/weevil-warrior",
            },
          ],
        },
        {
          title: "Get Down!",
          description:
            "Get Down! is a top down 2D 3D hybrid game made with Unity.\
            I worked on this game with Jaden Goter, Matt Lowe, Erik Skoog, Tessa Hardin, and Gabe Eubanks.\
            This game was a submission to the 48th Ludum Dare game jam.\
            I worked on level design and sprite art.",
          src: "projectImages/get_down.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://camdeno.itch.io/get-down",
            },
          ],
        },
        {
          title: "Whiz Blade",
          description:
            "Whiz Blade is a top down 2D puzzle game made with Unity.\
            I worked on this game with Jaden Goter, Erik Skoog, Zach Randolph, and Matt Lowe.\
            This game was a submission to the GMTK Game Jam 2020.\
            We received 143rd place out of 5,299 entries.\
            I worked on level design and sprite art.",
          src: "projectImages/whiz_blade.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://camdeno.itch.io/whiz-blade",
            },
          ],
        },
        {
          title: "Squatch Watch",
          description:
            "Squatch Watch is a 3D stealth game with with Unity.\
            I worked on this game with Jaden Goter, Matt Lowe, Erik Skoog, and Grant Davis.\
            The game was a submission to 46th Ludum Dare game jam.\
            I worked on enemy AI and programming.",
          src: "projectImages/squatch_watch.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://grantimation.itch.io/squatch-watch",
            },
          ],
        },
        {
          title: "Flip Trip",
          description:
            "Flip Trip is a 2D platformer made with Unity.\
            I worked on this game with Jaden Goter, Matt Lowe, and Grant Davis.\
            This game was a submission to the Kansas State Game Jam 2020, where we received 2nd place.\
            I worked on game design and sprite art.",
          src: "projectImages/flip_trip.png",
          links: [
            {
              text: "Play on itch.io",
              url: "https://camdeno.itch.io/flip-trip",
            },
          ],
        },
      ],
      schoolProjects: [
        {
          title: "Pitivi",
          description:
            "In my second year of college, we contributed to the open source video editor called Pitivi.\
            My team worked on a ticket for adding some safety boxes that can be toggled to appear in the video editor.",
          src: "projectImages/pitivi.png",
          links: [
            {
              text: "View Site",
              url: "https://www.pitivi.org/",
            },
          ],
        },
      ],
    };
  },
});
</script>

<style scoped>
.home-container {
  padding-bottom: 100px;
}

.scrollTarget {
  scroll-margin-top: 75px;
}

.projectList {
  padding-top: 50px;
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
