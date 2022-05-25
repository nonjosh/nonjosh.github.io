<template>
  <div class="parallax" :style="cssProps">
    <v-row align="center" justify="center" style="height: 100vh">
      <v-col class="text-center" cols="12">
        <h1 class="text-h4 font-weight-thin mb-4">Hi, I am Johnson</h1>
        <h4 class="subheading">Welcome to my portfolio page</h4>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    localImgPath: require("@/assets/sky_bg.jpg")
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

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  
  height: 100vh
}
</style>