<template>
  <v-row align="center" justify="center" style="height: 100vh">
    <v-col class="text-center description" cols="6">
      <v-card class="text-center">
        <h1 class="text-h4 font-weight-thin mb-4">Introduction here</h1>
        <h4 class="subheading">Welcome to my portfolio page</h4>
      </v-card>
    </v-col>
    <v-col class="parallax" :style="cssProps" cols="6"></v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    localImgPath: require("@/assets/walkway_bg.jpg"),
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
.description {
  background-color: black;

  height: 100%;
}

.parallax {
  /* The image used */
  background-image: var(--background-image);

  background-size: contain;

  /* Set a specific height */
  /* min-height: 500px; */

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  height: 100%;
}
</style>
