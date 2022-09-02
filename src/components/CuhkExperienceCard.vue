<template>
  <v-card outlined variant="outlined" class="text-left">
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
</template>

<script>
export default {
  name: "CuhkExperienceCard",

  data: () => ({
    item: {
      color: "green",
      icon: "mdi-school",
      title: "BSc in Physics",
      period: "2012/9 - 2015/8",
      location: "The Chinese University of Hong Kong",
    },
  }),
};
</script>

<style>
</style>