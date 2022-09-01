<template>
  <v-card
    color="transparent"
    outlined
    class="
      no-gutters
      parallax
      text-center
      d-flex
      flex-column
      align-center
      justify-center
    "
    :style="cssProps"
  >
    <v-card-text>
      <div class="text-h3 text-md-h2 font-weight-bold">
        Hi, I am Johnson, a full stack developer.
      </div>
      <v-avatar class="profile" size="300">
        <v-img :src="profileImgLocalPath"></v-img>
      </v-avatar>
      <p class="text-h4 my-10">
        Welcome to my portfolio page. <br />
        I am a fast learning and self-taught developer who is always looking for
        new challenges.
      </p>
      <div class="text-h4 my-10">
        I am open to job market now. Feel free to check out my CV below.
      </div>
      <v-row class="justify-center">
        <v-btn rounded outlined x-large text class="mx-2" :href="emailUrl">
          Email <v-icon right> mdi-email </v-icon>
        </v-btn>
        <v-btn rounded outlined x-large text class="mx-2" :href="linkedinUrl">
          LinkedIn <v-icon right> mdi-account </v-icon>
        </v-btn>
        <v-btn rounded outlined x-large text class="mx-2" :href="githubUrl">
          Github <v-icon right> mdi-github </v-icon>
        </v-btn>
        <v-btn rounded outlined x-large class="mx-2" :href="cvFilePath">
          CV <v-icon right> mdi-download </v-icon>
        </v-btn>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "AboutSection",
  data: () => ({
    bgImgLocalPath: require("@/assets/img/sky_bg.jpg"),
    profileImgLocalPath: require("@/assets/img/profile_awards.jpg"),
    emailUrl: "mailto:nonjosh@gmail.com",
    linkedinUrl: "https://www.linkedin.com/in/nonjosh/",
    githubUrl: "https://github.com/nonjosh",
    cvFilePath: "WongChongSangJohnson_20220824.pdf",
  }),
  computed: {
    cssProps() {
      return {
        "--background-image": `url(${this.bgImgLocalPath})`,
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
  min-height: 100vh;

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  /* height: 100%; */
}
</style>