<template>
  <v-card class="skill-section pt-10">
    <SkillTreeCard />
    <v-card-text class="text-center">⭐ = Skills that I am using most recently</v-card-text>
  </v-card>
</template>

<script>
import SkillTreeCard from "@/components/SkillTreeCard";

export default {
  name: "SkillsSection",

  components: { SkillTreeCard },
};
</script>

<style scoped>
.skill-section {
  height: 100vh;
  overflow-y: scroll;
}
</style>