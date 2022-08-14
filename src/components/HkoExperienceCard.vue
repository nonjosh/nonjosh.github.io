<template>
  <v-card outlined variant="outlined" class="text-left">
    <v-card-title :class="`font-weight-bold ${item.color}--text`">
      Analyst Programmer (T-Contract)
    </v-card-title>

    <v-card-subtitle class="font-weight-bold">
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <span v-bind="attrs" v-on="on">
            Hong Kong Observatory / Tsum Sha Tsui, Hong Kong
          </span>
        </template>
        The Hong Kong Observatory is a weather forecast agency of the government
        of Hong Kong. The Observatory forecasts the weather and issues warnings
        on weather-related hazards.
      </v-tooltip>
    </v-card-subtitle>

    <v-card-text>
      <!-- Display job description -->
      <p >
        <ul>
          <li>
            Developing new deep learning applications (including full-stacked website developments with VueJS and Python)
          </li>
          <li>
            Responsible for requirements capture, design, coding, testing, installation, documentation, server setup and maintenance
          </li>
          <li>
            Communicating with service and hardware provider companies
          </li>
          <li>
            Mentoring interns and new colleagues
          </li>
          <li>
            Prepare documentations and presentation materials
          </li>
          <li>
            Developing and maintaining other side projects (e.g. Smart Lamppost) with Go, ExpressJS
          </li>
        </ul>
      </p>

      <span class="font-weight-bold">Highlighted Projects</span>
      
      <v-expansion-panels focusable>
        <v-expansion-panel>
          <v-expansion-panel-header>Smart Weather Analytics Platform</v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Setup a platform for weather impact analytics</p>
            <ul>
              <li>Developed a system for analyzing different impact of weather</li>
              <li>Developed a webpage for visualizing the model results and raw data (with Vue JS)</li>
              <li>Setup GPU workstations and development environments for colleagues’ AI projects</li>
              <li>Communicated with vendors to setup clusters of GPU servers and database servers in HKO main server room</li>
              <li>Mentored interns and new colleagues </li>
              <li>Cooperated with colleagues in different IoT and AI projects</li>
            </ul>
          </v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header>Traffic Analytics</v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Real-time traffic data and weather impact analytics</p>
            <ul>
              <li>Developed a real-time NLP program for analyzing traffic condition from text provided in different news website (e.g. RTHK, 881903)</li>
              <li>Developed a real-time image recognition program for analyzing traffic condition from traffic snapshot images provided by the Transport Department</li>
              <li>Developed time series models for analyzing impact of rainfall on traffic condition</li>
              <li>Visualized the model result and raw data on webpages (with EmberJS and VueJS)</li>
            </ul>
          </v-expansion-panel-content>
        </v-expansion-panel>
        <v-expansion-panel>
          <v-expansion-panel-header>Flooding Analytics</v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Real-time image segmentation applications for flooding alerts</p>
            <ul>
              <li>Developed a real-time image recognition program for analyzing risk of flooding from water photos provided by the Drainage Services Department</li>
              <li>Visualized and quantized the water level on webpage (with VueJS)</li>
              <li>Cooperated with different teams, designed and setup a data pipeline architecture for the system</li>
              <li>MinIO database server maintenance</li>
            </ul>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "HungHingExperienceCard",
  data: () => ({
    item: {
      color: "blue",
    },
  }),
};
</script>
