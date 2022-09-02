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
        <v-col col="6"><SkillSection id="skill-section" /></v-col>
      </v-row>
      <v-row class="no-gutters experience-section" id="exp-section">
        <v-col cols="12" lg="9">
          <ExperienceSection id="experience-section" />
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
    <v-btn
      v-if="ready"
      elevation="2"
      fab
      fixed
      right
      bottom
      color="primary"
      @click="fabScrollNext()"
    >
      <v-icon v-if="nextSectionIndex == 0">mdi-arrow-up</v-icon>
      <v-icon v-else>mdi-arrow-down</v-icon>
    </v-btn>
  </v-app>
</template>

<script>
import AboutSection from "@/components/AboutSection.vue";
import SkillSection from "@/components/SkillSection.vue";
import ExperienceSection from "@/components/ExperienceSection.vue";
import ParallaxImg from "@/components/ParallaxImg";
import ShowcaseSection from "@/components/ShowcaseSection.vue";

export default {
  name: "App",

  components: {
    AboutSection,
    SkillSection,
    ExperienceSection,
    ParallaxImg,
    ShowcaseSection,
  },

  data: () => ({
    navList: [
      { title: "TOP", section_id: "about-section" },
      { title: "Skills", section_id: "skill-section" },
      { title: "Experiences", section_id: "exp-section" },
      { title: "Awards", section_id: "awards-section" },
      { title: "Showcases", section_id: "showcase-section" },
      // { title: "Origami" },
    ],
    bgImg: {
      localImgPath: require("@/assets/img/walkway_bg.jpg"),
      bgPosition: "40vw",
    },
    currentScroll: 0,
    ready: false
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
    fabScrollNext() {
      // Scroll to next section
      this.scrollSection(this.nextSectionId);
    },
  },

  computed: {
    desktopNavList() {
      return this.navList.filter((item) => item.title !== "Skills");
    },
    sectionPositionList() {
      // 0,0,995,1658,2975
      return this.navList.map((item) => {
        return document.getElementById(item.section_id).offsetTop;
      });
    },
    currentSectionId() {
      // Get current section id
      return this.navList.find((item, index) => {
        // Return last section if index is last
        if (index === this.navList.length - 1) {
          return true;
        }
        // Return section if currentScroll is between section positions
        return (
          this.currentScroll >=
            document.getElementById(item.section_id).offsetTop &&
          this.currentScroll <
            document.getElementById(this.navList[index + 1].section_id)
              .offsetTop
        );
      }).section_id;
    },
    currentSectionIndex() {
      // Get current section index
      return this.navList.findIndex((item) => {
        return item.section_id === this.currentSectionId;
      });
    },
    nextSectionIndex() {
      // Get next section index
      // If reach last section, scroll to top
      return this.currentSectionIndex === this.navList.length - 1
        ? 0
        : this.currentSectionIndex + 1;
    },
    nextSectionId() {
      // Get next section id
      return this.navList[this.nextSectionIndex].section_id;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
    this.ready = true
  },
};
</script>

<style scoped>
.v-sheet.v-toolbar {
  box-shadow: none !important;
}
</style>
