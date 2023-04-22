<template>
  <v-card outlined variant="outlined" class="text-left blue-card">
    <!-- Display period for mobile devices -->
    <v-card-title :class="`font-weight-bold ${item.color}--text`">
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <span v-bind="attrs" v-on="on">
            <v-icon left class="d-lg-none">{{item.icon}}</v-icon>{{ item.location }}
          </span>
        </template>
        {{ item.locationTooltip }}
      </v-tooltip>
    </v-card-title>

    <v-card-subtitle class="font-weight-bold">
      {{ item.title}} <span class="d-lg-none">({{ item.period }})</span>
    </v-card-subtitle>

    <v-card-text>
      <!-- Display job description -->

      <span class="font-weight-bold">Duties</span>
      <p >
        <ul>
          <li>
            Siri pipeline monitoring team.
          </li>
        </ul>
      </p>
      
      <!-- Technologies/SKills used -->
      <p>
        <v-chip class="ma-1" color="primary">CI/CD</v-chip>
        <v-chip class="ma-1" color="secondary">DevOps</v-chip>
      </p>

      <p>
        <v-chip class="ma-1" color="primary">Python</v-chip>
        <v-chip class="ma-1" color="secondary">Swift</v-chip>
        <v-chip class="ma-1" color="primary"><v-icon left> mdi-database </v-icon>PostgreSQL</v-chip>
        <v-chip class="ma-1" color="primary"><v-icon left> mdi-cloud </v-icon>GCP</v-chip>
      </p>

    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "AppleExperienceCard",
  data: () => ({
    item: {
      color: "white",
      icon: "mdi-briefcase",
      period: "2023/2 - Present",
      title: "Software Development Engineer II (Contract)",
      location: "Apple Inc.",
      locationTooltip:
        "Apple Inc. is an American multinational technology company headquartered in Cupertino, California.",
    },
  }),
};
</script>

<style scoped>
.blue-card.v-sheet.v-card {
  border: thin solid white;
}
</style>
