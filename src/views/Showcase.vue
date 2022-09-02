<template>
  <!-- TODO Showcase section-->
  <v-card outlined class="pt-5 showcase-section">
    <center><h1 class="py-10"><u>My Personal Projects</u></h1></center>
    <v-row>
      <v-col cols="12" lg="6">
        <v-card outlined>
          <v-img
            :src="require('@/assets/img/acgn-bot_screenshot.png')"
            class="pa-10"
            max-height="50vh"
            max-width="500px"
          />
          <v-card-title>ACGN bot</v-card-title>
          <v-card-text>
            <p>This is a bot that I made for subscribing updates in ACGN.</p>
            <p>
              It performs web-scraping on many websites and notices me when
              there is a new episode.
            </p>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12" lg="6">
        <v-card outlined>
          <v-img
            :src="require('@/assets/img/dnd-data_screenshot.png')"
            class="ma-5"
            aspect-ratio="1.7"
          />
          <v-card-title>DnD database</v-card-title>
          <v-card-text>
            <p>
              This is a webpage that I made for searching the board game (Dragon and Dungeon 4.0) rules and
              other information.
            </p>
            <p>Simple sorting and filtering functions are implemented.</p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6">
        <v-card outlined>
          <v-img
            :src="require('@/assets/img/dnd-online_screenshot.png')"
            class="ma-5"
            aspect-ratio="1.7"
          />
          <v-card-title>DnD Online (In Progress)</v-card-title>
          <v-card-text>
            <p>
              This is a webpage that I made for playing the board game (Dragon and Dungeon 4.0) with friends.
            </p>
            <p>Different users (4 of us) can share the same game section and combat information together in real time</p>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12" lg="6">
        <v-card outlined>
          <v-img
            src="https://www.highcharts.com/demo/images/samples/stock/demo/stock-tools-gui/thumbnail.png"
            class="ma-5"
            aspect-ratio="1.7"
          />
          <v-card-title>Trading bot (In Progress)</v-card-title>
          <v-card-text>
            <p>
              This is a bot that I made for trading stocks and crypto
              currencies.
            </p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  name: "ShowcaseSection",

  data: () => ({
    ecosystem: [
      {
        text: "vuetify-loader",
        href: "https://github.com/vuetifyjs/vuetify-loader",
      },
      {
        text: "github",
        href: "https://github.com/vuetifyjs/vuetify",
      },
      {
        text: "awesome-vuetify",
        href: "https://github.com/vuetifyjs/awesome-vuetify",
      },
    ],
    importantLinks: [
      {
        text: "Chat",
        href: "https://community.vuetifyjs.com",
      },
      {
        text: "Made with Vuetify",
        href: "https://madewithvuejs.com/vuetify",
      },
      {
        text: "Twitter",
        href: "https://twitter.com/vuetifyjs",
      },
      {
        text: "Articles",
        href: "https://medium.com/vuetify",
      },
    ],
    whatsNext: [
      {
        text: "Explore components",
        href: "https://vuetifyjs.com",
      },
      {
        text: "Roadmap",
        href: "https://vuetifyjs.com/introduction/roadmap/",
      },
      {
        text: "Frequently Asked Questions",
        href: "https://vuetifyjs.com/getting-started/frequently-asked-questions",
      },
    ],
  }),
};
</script>

<style scoped>
.showcase-section {
  height: 180vh;
}
</style>