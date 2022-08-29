<template>
  <v-row class="no-gutters fill-height launch-section">
    <v-col
      cols="12"
      lg="6"
      class="
        parallax
        fill-height
        text-center
        d-flex
        flex-column
        align-center
        justify-center
      "
      :style="cssProps"
    >
      <v-card color="transparent" outlined>
        <v-card-text>
          <div class="text-h3 text-md-h2 font-weight-bold">
            Hi, I am Johnson, a full stack developer.
          </div>
          <v-avatar class="profile" size="300">
            <v-img :src="profileImgLocalPath"></v-img>
          </v-avatar>
          <p class="text-h4 my-10">
            Welcome to my portfolio page. <br />
            I am a fast learning and self-taught developer who is always looking
            for new challenges.
          </p>
          <div class="text-h4 my-10">
            I am open to job market now. Feel free to check out my CV below.
          </div>
          <v-row class="justify-center">
            <v-btn x-large text class="mx-2" :href="emailUrl">
              Email <v-icon> mdi-email </v-icon>
            </v-btn>
            <v-btn x-large text class="mx-2" :href="linkedinUrl">
              LinkedIn <v-icon> mdi-account </v-icon>
            </v-btn>
            <v-btn x-large text class="mx-2" :href="githubUrl">
              Github <v-icon> mdi-github </v-icon>
            </v-btn>
            <v-btn x-large class="mx-2" :href="cvFilePath">
              CV <v-icon> mdi-download </v-icon>
            </v-btn>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
    <!-- TODO add awards -->
    <v-col cols="6">
      <v-card class="
        fill-height
        text-center
        align-center
        justify-center scroll">
        <v-card-title >
        </v-card-title>
        <v-card-title >
        </v-card-title>
        <SkillTreeCard class="text-left" />
      </v-card>
    </v-col>
  </v-row>
  <!-- TODO arrow button for jumping to next section -->
</template>

<script>
import SkillTreeCard from "@/components/SkillTreeCard";

export default {
  components: { SkillTreeCard },
  data: () => ({
    bgImgLocalPath: require("@/assets/img/sky_bg.jpg"),
    bgImgLocalPath2: require("@/assets/img/leaf_bg.jpg"),
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
.launch-section {
  height: 102vh;
}
.parallax {
  /* The image used */
  background-image: var(--background-image);
  /* background-image: url("img/sky_bg.jpg"); */

  background-size: contain;

  /* Set a specific height */
  /* min-height: 500px; */

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  /* height: 100%; */
}

.text-h1 {
  font-size: 3rem;
}

.scroll {
  overflow-y: scroll;
  height: 102vh;
  width: 50vw;
}
</style>
