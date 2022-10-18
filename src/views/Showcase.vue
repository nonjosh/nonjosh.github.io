<template>
  <v-card outlined class="py-5">
    <center>
      <h1 class="py-10"><u>My Personal Projects</u></h1>
    </center>
    <v-row>
      <v-col cols="12" lg="6">
        <v-card outlined @click="showPreview(items[0].imgSrc)">
          <v-img
            :src="items[0].imgSrc"
            class="ma-5 d-none d-md-block"
            max-height="50vh"
            max-width="500px"
          />
          <v-card-title> {{ items[0].title }} </v-card-title>
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
        <v-card outlined @click="showPreview(items[1].imgSrc)">
          <v-img
            :src="items[1].imgSrc"
            class="ma-5 d-none d-md-block"
            aspect-ratio="1.7"
          />
          <v-card-title> {{ items[1].title }} </v-card-title>
          <v-card-text>
            <p>
              This is a webpage that I made for searching the board game (Dragon
              and Dungeon 4.0) rules and other information.
            </p>
            <p>Simple sorting and filtering functions are implemented.</p>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" lg="6">
        <v-card outlined @click="showPreview(items[2].imgSrc)">
          <v-img
            :src="items[2].imgSrc"
            class="ma-5 d-none d-md-block"
            aspect-ratio="1.7"
          />
          <v-card-title> {{ items[2].title }} </v-card-title>
          <v-card-text>
            <p>
              This is a webpage that I made for playing the board game (Dragon
              and Dungeon 4.0) with friends.
            </p>
            <p>
              Different users (4 of us) can share the same game section and
              combat information together in real time
            </p>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12" lg="6">
        <v-card outlined @click="showPreview(items[3].imgSrc)">
          <v-img
            :src="items[3].imgSrc"
            class="ma-5 d-none d-md-block"
            aspect-ratio="1.7"
          />
          <v-card-title> {{ items[3].title }} </v-card-title>
          <v-card-text>
            <p>
              This is a bot that I made for trading stocks and crypto
              currencies.
            </p>
          </v-card-text>
        </v-card>
      </v-col>

      <v-overlay :z-index="zIndex" :value="overlay">
        <v-img
          contain
          :src="previewImgSrc"
          max-height="100vh"
          max-width="100vw"
          @click="overlay = false"
        />
      </v-overlay>
    </v-row>
  </v-card>
</template>

<script>
export default {
  name: "ShowcaseSection",

  data: () => ({
    overlay: false,
    zIndex: 1,
    previewImgSrc: "",
    items: [
      {
        id: 0,
        title: "ACGN bot",
        description:
          "This is a bot that I made for subscribing updates in ACGN.",
        imgSrc: require("@/assets/img/acgn-bot_screenshot.png"),
      },
      {
        id: 1,
        title: "DnD database",
        description:
          "This is a webpage that I made for searching the board game (Dragon and Dungeon 4.0) rules and other information.",
        imgSrc: require("@/assets/img/dnd-data_screenshot.png"),
      },
      {
        id: 2,
        title: "DnD Online (In Progress)",
        description:
          "This is a webpage that I made for playing the board game (Dragon and Dungeon 4.0) with friends.",
        imgSrc: require("@/assets/img/dnd-online_screenshot.png"),
      },
      {
        id: 3,
        title: "Algotrade System (In Progress)",
        description:
          "This is a algotrade bot that I am making for portfolio management (stocks, crypto currencies etc).",
        imgSrc: require("@/assets/img/algotrade-Architecture.drawio.png"),
      },
    ],
  }),

  methods: {
    showPreview(imgSrc) {
      this.previewImgSrc = imgSrc;
      this.overlay = true;
    },
  },
};
</script>
