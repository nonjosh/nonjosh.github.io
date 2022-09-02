<template>
  <v-card outlined variant="outlined" class="text-left">
    <!-- Display period for mobile devices -->
    <v-card-title :class="`font-weight-bold ${item.color}--text`">
      <v-icon left class="d-lg-none">{{ item.icon }}</v-icon
      >{{ item.location }}
    </v-card-title>

    <v-card-subtitle class="font-weight-bold">
      {{ item.title }} <span class="d-lg-none">({{ item.period }})</span>
    </v-card-subtitle>

    <v-card-text>
      <!-- Display job description -->
      <p v-if="item.description" class="my-10">
        {{ item.description }}
      </p>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "CuhkExperienceCard",

  data: () => ({
    item: {
      color: "green",
      icon: "mdi-school",
      period: "2012/9 - 2015/8",
      title: "BSc in Physics",
      location: "The Chinese University of Hong Kong",
    },
  }),
};
</script>

<style>
</style>