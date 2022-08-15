<template>
  <!-- TODO Experience Section -->
  <v-row class="no-gutters experience-section align-center">
    <v-col cols="12" lg="9" class="fill-height text-center justify-center">
      <v-card class="fill-height text-center d-flex flex-column justify-center">
        <h1><u>My Experiences</u></h1>

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
            <v-card
              v-if="item.id == 0"
              outlined
              variant="outlined"
              class="text-left"
            >
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
                <!-- TODO add highlighed projects -->
              </v-card-text>
            </v-card>
            <HungHingExperienceCard v-if="item.id == 1" />
            <HkoExperienceCard v-if="item.id == 2" />
          </v-timeline-item>
        </v-timeline>
        <hr />
        <h1><u>Awards</u><v-icon> mdi-medal </v-icon></h1>
        <h2 class="mt-10">
          2019 Hong Kong ICT Awards: Smart Business - Gold Award Smart Planning
        </h2>
        <v-card-text>
          Reference:
          <a
            href="https://www.hkictawards.hk/doc_2019/booklet/General_Award_Programme_2019.pdf"
            >https://www.hkictawards.hk/doc_2019/booklet/General_Award_Programme_2019.pdf</a
          >(p31)
        </v-card-text>
        <h2 class="mt-10">
          Hong Kong IDC Digital Transformation Awards Winner 2019
        </h2>
        <h2>Operating Model Master for Hong Kong</h2>
        <v-card-text>
          Reference:
          <a href="https://whatsnew.hunghingprinting.com/hung-hing-wins-idc-digital-transformation-award-two-years-in-a-row/"
            >https://whatsnew.hunghingprinting.com/hung-hing-wins-idc-digital-transformation-award-two-years-in-a-row/</a
          >
        </v-card-text>
      </v-card>
    </v-col>
    <v-col cols="3" class="fill-height d-none d-lg-block">
      <ParallaxImg
        :localImgPath="bgImg.localImgPath"
        :bgPosition="bgImg.bgPosition"
      />
    </v-col>
  </v-row>
</template>

<script>
import ParallaxImg from "@/components/ParallaxImg";
import HungHingExperienceCard from "@/components/HungHingExperienceCard";
import HkoExperienceCard from "@/components/HkoExperienceCard";

export default {
  name: "ExperienceSection",

  components: { ParallaxImg, HungHingExperienceCard, HkoExperienceCard },

  data: () => ({
    bgImg: {
      localImgPath: require("@/assets/img/walkway_bg.jpg"),
      bgPosition: "40vw",
    },
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

<style scoped>
.experience-section {
  height: 200vh;
}
</style>