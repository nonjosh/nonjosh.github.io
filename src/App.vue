<template>
  <v-app>
    <v-app-bar dense fixed color="transparent">
      <v-spacer></v-spacer>
      <!-- buttons for Desktop -->
      <v-btn
        text
        class="d-none d-md-block"
        v-for="item in desktopNavList"
        :key="item.section_id"
        @click="scrollSection(item.section_id)"
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
            v-for="(item, index) in navList"
            :key="index"
            :value="index"
          >
            <v-list-item-title @click="scrollSection(item.section_id)">
              {{ item.title }}
            </v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <v-row class="no-gutters">
        <v-col col="6"><AboutSection id="about-section" /></v-col>
        <v-col col="6"><SkillsSection id="skill-section" /></v-col>
      </v-row>
      <v-row class="no-gutters">
        <v-col cols="12" lg="9">
          <ExperiencesSection id="experience-section" />
          <AwardsSection id="awards-section" />
        </v-col>
        <v-col lg="3" class="d-none d-lg-block">
          <ParallaxImg
            :localImgPath="bgImg.localImgPath"
            :bgPosition="bgImg.bgPosition"
          />
        </v-col>
      </v-row>
      <ShowcaseSection id="showcase-section" />
    </v-main>
    <FabBtn
      v-if="ready"
      :navList="navList"
      :currentScroll="currentScroll"
      :scrollSection="scrollSection"
    />
  </v-app>
</template>

<script>
import AboutSection from "@/views/About.vue";
import SkillsSection from "@/views/Skills.vue";
import ExperiencesSection from "@/views/Experiences.vue";
import ShowcaseSection from "@/views/Showcase.vue";
import AwardsSection from "@/views/Awards.vue";
import ParallaxImg from "@/components/ParallaxImg";
import FabBtn from "@/components/FabBtn";

export default {
  name: "App",

  components: {
    AboutSection,
    SkillsSection,
    ExperiencesSection,
    AwardsSection,
    ShowcaseSection,
    ParallaxImg,
    FabBtn,
  },

  data: () => ({
    navList: [
      { title: "TOP", section_id: "about-section" },
      { title: "Skills", section_id: "skill-section" },
      { title: "Experiences", section_id: "experience-section" },
      { title: "Awards", section_id: "awards-section" },
      { title: "Showcases", section_id: "showcase-section" },
      // { title: "Origami" },
    ],
    bgImg: {
      localImgPath: require("@/assets/img/walkway_bg.jpg"),
      bgPosition: "40vw",
    },
    currentScroll: 0,
    ready: false,
  }),

  methods: {
    onScroll() {
      // Update currentScroll on scroll
      this.currentScroll = window.top.scrollY;
    },
    scrollSection(id) {
      // Scroll to section by id
      document.getElementById(id).scrollIntoView({
        behavior: "smooth",
      });
    },
  },

  computed: {
    desktopNavList() {
      return this.navList.filter((item) => item.title !== "Skills");
    },
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
    this.ready = true;
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll);
  },
};
</script>

<style scoped>
.v-sheet.v-toolbar {
  box-shadow: none !important;
}
</style>
