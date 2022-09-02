<template>
  <v-card class="pa-10" outlined>
    <h1 class="text-center font-weight-bold yellow--text"><u>Awards</u></h1>
    <v-card v-for="awardItem in awards" :key="awardItem.id">
      <v-card-text>
        <h2 class="mt-5 yellow--text">
          <v-icon left>mdi-medal</v-icon>{{ awardItem.title }}
        </h2>
        <span v-if="awardItem.reference" class="my-10">
          <a :href="awardItem.Reference" target="_blank">Reference</a>
          <font v-if="awardItem.page"> (P. {{ awardItem.page }})</font>
        </span>
      </v-card-text>
    </v-card>
  </v-card>
</template>

<script>
export default {
  name: "AwardsCard",
  data: () => ({
    awards: [
      {
        id: 0,
        title:
          "2019 Hong Kong ICT Awards: Smart Business - Gold Award Smart Planning",
        reference:
          "https://www.hkictawards.hk/doc_2019/booklet/General_Award_Programme_2019.pdf",
        page: 31,
      },
      {
        id: 1,
        title: "Hong Kong IDC Digital Transformation Awards Winner 2019",
        reference:
          "https://whatsnew.hunghingprinting.com/hung-hing-wins-idc-digital-transformation-award-two-years-in-a-row/",
      },
    ],
  }),
};
</script>

<style>
</style>