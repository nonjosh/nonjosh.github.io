<template>
  <v-card class="text-center fill-height">
    <h1 class="pa-10"><u>My Experiences</u></h1>

    <!-- Show Experience Timeline for desktop/tablet devices only -->
    <ExperienceTimeline class="d-none d-md-block" />
    <!-- Show Experience Cards for mobile devices -->
    <HkoExperienceCard class="d-md-none" />
    <HungHingExperienceCard class="d-md-none" />
    <CuhkExperienceCard class="d-md-none" />

    <!-- Awards Card -->
    <AwardsCard id="awards-section" />
  </v-card>
</template>

<script>
import ExperienceTimeline from "@/components/ExperienceTimeline.vue";
import HkoExperienceCard from "@/components/HkoExperienceCard.vue";
import HungHingExperienceCard from "@/components/HungHingExperienceCard.vue";
import CuhkExperienceCard from "@/components/CuhkExperienceCard.vue";
import AwardsCard from "@/components/AwardsCard.vue";

export default {
  name: "ExperienceSection",

  components: {
    ExperienceTimeline,
    HkoExperienceCard,
    HungHingExperienceCard,
    CuhkExperienceCard,
    AwardsCard,
  },
};
</script>
