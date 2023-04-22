<template>
  <v-card class="text-center" outlined>
    <h1 class="pa-10"><u>My Experiences</u></h1>

    <!-- Show Experience Timeline for desktop/tablet devices only -->
    <ExperienceTimeline class="d-none d-md-block" />
    <!-- Show Experience Cards for mobile devices -->
    <AppleExperienceCard class="d-md-none" />
    <HkoExperienceCard class="d-md-none" />
    <HungHingExperienceCard class="d-md-none" />
    <CuhkExperienceCard class="d-md-none" />
  </v-card>
</template>

<script>
import ExperienceTimeline from "@/components/ExperienceTimeline.vue";
import AppleExperienceCard from "@/components/AppleExperienceCard.vue";
import HkoExperienceCard from "@/components/HkoExperienceCard.vue";
import HungHingExperienceCard from "@/components/HungHingExperienceCard.vue";
import CuhkExperienceCard from "@/components/CuhkExperienceCard.vue";

export default {
  name: "ExperiencesSection",

  components: {
    ExperienceTimeline,
    AppleExperienceCard,
    HkoExperienceCard,
    HungHingExperienceCard,
    CuhkExperienceCard,
  },
};
</script>
