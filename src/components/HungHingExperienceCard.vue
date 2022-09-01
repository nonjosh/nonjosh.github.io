<template>
  <v-card outlined variant="outlined" class="text-left red-card">
    <v-card-title :class="`font-weight-bold ${item.color}--text`">
      Junior Developer
    </v-card-title>

    <v-card-subtitle class="font-weight-bold">
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <span v-bind="attrs" v-on="on">
            Hung Hing Off-Set Printing Group Limited / Tai Po, Hong Kong
          </span>
        </template>
        60+ years Printing and Manufacture Local Company listed on the Hong Kong
        Stock Exchange (SEHK: 450)
      </v-tooltip>
    </v-card-subtitle>

    <v-card-text>
      <!-- Display job description -->
      <p>
        <ul>
          <li>
            Working in the Hong Kong main office and visiting mainland offices
            if needed.
          </li>
          <li>
            Developing new applications (mobile app and websites) for
            factory workers, office colleagues and customers.
          </li>
          <li>
            Responsible for requirements capture, design, coding, testing,
            installation.
          </li>
          <li>
            Acting as a bridge between colleagues and vendors for outsourced
            mobile app and websites.
          </li>
          <li>
            Providing support & maintenance of existing Java programs, MySQL
            databases, mobile apps (iOS and Android), websites and other
            application servers.
          </li>
        </ul>
      </p>

      <p>
        <v-chip color="warning">2019 HKICT Gold Award</v-chip>
      </p>
  
      <p>
        <v-chip class="ma-1" color="primary">Andoid</v-chip>
        <v-chip class="ma-1" color="secondary">iOS</v-chip>
        <v-chip class="ma-1" color="secondary">Websites</v-chip>
      </p>

      <p>
        <v-chip class="ma-1" color="primary">Java</v-chip>
        <v-chip class="ma-1" color="secondary">PHP</v-chip>
        <v-chip class="ma-1" color="secondary">Objective-C</v-chip>
        <v-chip class="ma-1" color="primary">Oracle Database</v-chip>
      </p>

      <!-- TODO add highlighed projects -->
      <span class="font-weight-bold">Highlighted Projects</span>
      <v-expansion-panels focusable>
        <v-expansion-panel>
          <v-expansion-panel-header>
            Industrial Revolution 4.0 - IoT implementation in factory machines
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            <v-chip class="ma-1" color="warning">2019 Hong Kong ICT Awards: Smart Business - Gold Award</v-chip>
            <p>initiating the concept of Industry 4.0 in the company</p>
            <ul>
              <li>Introduced Machine Operator Console App for over hundreds of factory machines to replace paper-based process, record real-time production data and analysis data for improving OEE (Overall Equipment Effectiveness).</li>
              <li>Developed IoT program, Tablet App (Android) and monitoring page (for TV screens) in multi-factories in HK and mainland China.</li>
              <li>Centralized big data from IoT devices across multi-factories.</li>
              <li>Designed network architecture and set up servers.</li>
              <li>Developed mobile app (iOS and Android) for visualizing real-time factory machines status and job progress for management levels.</li>
              <li>Developed notification and chat room functions to ease communication between colleagues, thus to minimize unplanned idle time of machines.</li>
            </ul>
          </v-expansion-panel-content>
        </v-expansion-panel>
        
        <v-expansion-panel>
          <v-expansion-panel-header>Picking List Mobile App</v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Implementing mobile app solutions to replace paper-based processes in the factories</p>
            <ul>
              <li>Developed mobile app (iOS and Android) for production line and warehouse workers (>100) to handle the applications of materials picking requests.</li>
              <li>Developed shopping cart function to ease the request process.</li>
              <li>Developed TV screens for warehouse workers.</li>
              <li>Cooperated with vendors to improve UX and enhance functionalities.</li>
            </ul>

          </v-expansion-panel-content>
        </v-expansion-panel>

        <v-expansion-panel>
          <v-expansion-panel-header>Local Delivery Mobile App </v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Implementing mobile app solutions to replace paper-based processes</p>
            <ul>
              <li>Developed mobile app (Android) for Hong Kong local drivers to record delivery history everyday.</li>
              <li>Developed email functions for notifying applicants the completion of delivery jobs.</li>
              <li>Visualized the driver performance through dashboards.</li>
              <li>Cooperated with vendors to improve UX and enhance functionalities.</li>
            </ul>
          </v-expansion-panel-content>
        </v-expansion-panel>

        <v-expansion-panel>
          <v-expansion-panel-header>Warehouse Management System Mobile App</v-expansion-panel-header>
          <v-expansion-panel-content>
            <p>Implementing mobile app solutions to replace paper-based processes in the factories</p>
            <ul>
              <li>Developed mobile app (Android) for warehouse workers to handle part of the stock managements if factories</li>
              <li>Implemented QR code technology to raise usability and accuracy.</li>
              <li>Involved in discussion and design of the solution with factory users.</li>
              <li>Cooperated with vendors and led trainee developer to meet project deadlines.</li>
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
      color: "red",
    },
  }),
};
</script>

<style scoped>
.red-card.v-sheet.v-card {
  border: thin solid red;
}
</style>