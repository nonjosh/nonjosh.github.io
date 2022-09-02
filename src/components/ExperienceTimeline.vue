<template>
  <v-timeline side="end" class="ma-10">
    <v-timeline-item
      v-for="item in items.slice().reverse()"
      :key="item.id"
      :icon="item.icon"
      :color="item.color"
    >
      <!-- Display period -->
      <template v-slot:opposite>
        <span
          :class="`headline font-weight-bold ${item.color}--text`"
          v-text="item.period"
        ></span>
      </template>

      <!-- Display job/school content -->
      <CuhkExperienceCard v-if="item.id == 0" />
      <HungHingExperienceCard v-if="item.id == 1" />
      <HkoExperienceCard v-if="item.id == 2" />
    </v-timeline-item>
  </v-timeline>
</template>

<script>
import CuhkExperienceCard from "@/components/CuhkExperienceCard.vue";
import HungHingExperienceCard from "@/components/HungHingExperienceCard";
import HkoExperienceCard from "@/components/HkoExperienceCard";

export default {
  name: "ExperienceTimeline",

  components: { CuhkExperienceCard, HungHingExperienceCard, HkoExperienceCard },
  data: () => ({
    items: [
      {
        id: 0,
        color: "green",
        icon: "mdi-school",
        title: "BSc in Physics",
        period: "2012/9 - 2015/8",
        location: "The Chinese University of Hong Kong",
      },
      {
        id: 1,
        color: "red",
        icon: "mdi-briefcase",
        title: "Junior Developer",
        period: "2016/3 - 2019/9",
        location:
          "Hung Hing Off-Set Printing Group Limited / Tai Po, Hong Kong",
        description:
          "Developing new applications (mobile app and websites) for factory workers, office colleagues and customers",
      },
      {
        id: 2,
        color: "blue",
        icon: "mdi-briefcase",
        period: "2019/10 - 2022/2",
        title: "Analyst Programmer",
        location: "Hong Kong Observatory",
        companyDescription: "",
        description:
          "Developing new deep learning applications (including full-stacked website developments)",
      },
    ],
  }),
};
</script>

<style>
</style>