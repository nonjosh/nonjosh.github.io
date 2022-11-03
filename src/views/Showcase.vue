<template>
  <v-card outlined class="py-5">
    <center>
      <h1 class="py-10"><u>My Personal Projects</u></h1>
    </center>
    <v-row>
      <v-col v-for="item in items" :key="item.id" cols="12" lg="6">
        <v-card outlined @click="showPreview(item.imgSrc)">
          <v-img
            :src="item.imgSrc"
            class="ma-5 d-none d-md-block"
            aspect-ratio="1.7"
          />
          <v-card-title> {{ item.title }} </v-card-title>
          <v-card-text>
            <p v-if="item.badges">
              <v-chip
                v-for="badge in item.badges"
                :key="badge.id"
                class="ma-1"
                :color="badge.color"
              >
                {{ badge.desc }}
              </v-chip>
            </p>
            <p v-for="desc in item.desc" :key="desc">
              {{ desc }}
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
        imgSrc: require("@/assets/img/acgn-bot_screenshot.png"),
        badges: [
          { desc: "Telegram Bot", color: "primary" },
          { desc: "Web Scraping", color: "primary" },
          { desc: "Python", color: "secondary" },
        ],
        desc: [
          "This is a bot that I made for subscribing updates in anime, comics and novel websites.",
          "It performs web-scraping on many websites and send telegram message to me when there is a new episode.",
        ],
      },
      {
        id: 1,
        title: "DnD4e Data Catalog",
        imgSrc: require("@/assets/img/dnd-data_screenshot.png"),
        badges: [
          { desc: "Boardgame Data Catalog", color: "primary" },
          { desc: "Web Scraping", color: "secondary" },
          { desc: "VueJS", color: "secondary" },
        ],
        desc: [
          "This is a webpage that I made for searching the board game (Dragon and Dungeon 4.0 edition) rules and other information.",
          "Simple sorting and filtering functions are implemented.",
        ],
      },
      {
        id: 2,
        title: "DnD4e Online (In Progress)",
        imgSrc: require("@/assets/img/dnd-online_screenshot.png"),
        badges: [
          { desc: "Online Boardgame", color: "primary" },
          { desc: "Live Chat", color: "primary" },
          { desc: "VueJS", color: "secondary" },
        ],
        desc: [
          "This is a webpage that I made for playing the board game (Dragon and Dungeon 4.0 edition) with friends.",
          "Different users (4 of us) can share the same game section and combat information together in real time.",
        ],
      },
      {
        id: 3,
        title: "Algotrade System (In Progress)",
        imgSrc: require("@/assets/img/algotrade-Architecture.drawio.png"),
        badges: [
          { desc: "Algotrade", color: "primary" },
          { desc: "ETL", color: "primary" },
          { desc: "Python", color: "secondary" },
        ],
        desc: [
          "It is an algotrade system for portfolio management. It can get historical and real-time data from different sources, and perform backtesting and live trading. (HK stock market, US stock market, and crypto market)",
        ],
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
