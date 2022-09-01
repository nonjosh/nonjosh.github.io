<template>
  <v-card class="text-center fill-height">
    <h1 class="pa-10"><u>My Experiences</u></h1>
    <ExperienceTimeline />
    <AwardsCard id="awards-section" />
  </v-card>
</template>

<script>
import ExperienceTimeline from "@/components/ExperienceTimeline.vue";
import AwardsCard from "@/components/AwardsCard.vue";

export default {
  name: "ExperienceSection",

  components: { ExperienceTimeline, AwardsCard },
};
</script>
