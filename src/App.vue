<template>
  <v-app>
    <v-app-bar dense fixed outlined color="transparent">
      <v-spacer></v-spacer>
      <!-- buttons for Desktop -->
      <v-btn
        text
        class="d-none d-md-block"
        v-for="item in items"
        :key="item.section_id"
        @click="scroll(item.section_id)"
        >{{ item.title }}</v-btn
      >
      <!-- button for Mobiles -->
      <v-menu anchor="start">
        <template v-slot:activator="{ on, attrs }">
          <v-app-bar-nav-icon
            v-bind="attrs"
            v-on="on"
            class="d-md-none"
          ></v-app-bar-nav-icon>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in items"
            :key="index"
            :value="index"
          >
            <v-list-item-title @click="scroll(item.section_id)">{{
              item.title
            }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <LaunchSection id="launch" />
      <!-- <SkillSection id="skill-section" /> -->
      <ExperienceSection id="exp-section" />
      <ShowcaseSection id="showcase-section" />
    </v-main>
  </v-app>
</template>

<script>
import LaunchSection from "@/components/LaunchSection.vue";
// import SkillSection from "@/components/SkillSection.vue";
import ExperienceSection from "@/components/ExperienceSection.vue";
import ShowcaseSection from "@/components/ShowcaseSection.vue";

export default {
  name: "App",

  components: {
    LaunchSection,
    // SkillSection,
    ExperienceSection,
    ShowcaseSection,
  },

  data: () => ({
    title: "Temp Title",
    // navBarbgImgLocalPath: require("@/assets/sky_bg.jpg"),
    items: [
      { title: "TOP", section_id: "launch" },
      // { title: "Skills", section_id: "skill-section" },
      { title: "Experiences", section_id: "exp-section" },
      { title: "Showcases", section_id: "showcase-section" },
      // { title: "Origami" },
    ],
  }),

  methods: {
    scroll(id) {
      document.getElementById(id).scrollIntoView({
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
.v-sheet.v-toolbar {
  box-shadow: none !important;
}
</style>
