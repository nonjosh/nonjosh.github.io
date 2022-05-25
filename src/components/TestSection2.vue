<template>
  <v-row align="center" justify="center" style="height: 100vh">
    <v-col cols="6" class="parallax" :style="cssProps"></v-col>
    <v-col class="text-center" cols="6">
      <v-timeline side="end">
        <v-timeline-item v-for="item in items" :key="item.id" :dot-color="item.color" size="small">
          <v-alert :value="true" :color="item.color" :icon="item.icon" class="white--text">
            Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire
            principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi
            sententiae.
          </v-alert>
        </v-timeline-item>
      </v-timeline>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    localImgPath: require("@/assets/walkway_bg.jpg"),
    items: [
      {
        id: 1,
        color: 'info',
        icon: 'mdi-information',
      },
      {
        id: 2,
        color: 'error',
        icon: 'mdi-alert-circle',
      },
    ],
  }),
  computed: {
    cssProps() {
      return {
        "--background-image": `url(${this.localImgPath})`,
      };
    },
  },
};
</script>

<style scoped>
.parallax {
  /* The image used */
  background-image: var(--background-image);

  background-size: contain;

  /* Set a specific height */
  /* min-height: 500px; */
  max-width: 50%;

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: -50% 50%;
  background-repeat: no-repeat;
  background-size: cover;

  height: 100vh;
}
</style>