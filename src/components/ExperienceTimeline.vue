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
      <v-card v-if="item.id == 0" outlined variant="outlined" class="text-left">
        <v-card-title :class="`font-weight-bold ${item.color}--text`">
          {{ item.title }}
        </v-card-title>

        <v-card-subtitle class="font-weight-bold">
          {{ item.location }}
        </v-card-subtitle>

        <v-card-text>
          <!-- Display job description -->
          <p v-if="item.description" class="my-10">
            {{ item.description }}
          </p>
        </v-card-text>
      </v-card>
      <HungHingExperienceCard v-if="item.id == 1" />
      <HkoExperienceCard v-if="item.id == 2" />
    </v-timeline-item>
  </v-timeline>
</template>

<script>
import HungHingExperienceCard from "@/components/HungHingExperienceCard";
import HkoExperienceCard from "@/components/HkoExperienceCard";

export default {
  name: "ExperienceTimeline",
  
  components: {  HungHingExperienceCard, HkoExperienceCard },
  data: () => ({
    items: [
      {
        id: 0,
        color: "grey",
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