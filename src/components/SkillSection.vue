<template>
  <!-- TODO Skill section -->
  <v-row class="no-gutters skill-section align-center">
    <v-col class="fill-height d-none d-lg-block" cols="6">
      <ParallaxImg :localImgPath="localImgPath" />
    </v-col>
    <v-col class="fill-height" col="6">
      <SkillTreeCard />
    </v-col>
  </v-row>
</template>

<script>
import ParallaxImg from "@/components/ParallaxImg";
import SkillTreeCard from "@/components/SkillTreeCard";

export default {
  name: "SkillSection",

  components: { ParallaxImg, SkillTreeCard },

  data: () => ({
    localImgPath: require("@/assets/img/leaf_bg.jpg"),
  }),
};
</script>

<style scoped>
.skill-section {
  height: 102vh;
}
</style>
