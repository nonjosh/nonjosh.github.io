<template>
  <v-card class="fill-height parallax-bg" :style="cssProps"></v-card>
</template>

<script>
export default {
  name: "ParallaxImg",

  props: {
    localImgPath: {
      type: String,
      default: require("@/assets/img/leaf_bg.jpg"),
    },
    bgPosition: {
      type: String,
      default: "center",
    },
  },

  computed: {
    cssProps() {
      return {
        "--background-image": `url(${this.localImgPath})`,
        "--background-position": this.bgPosition,
      };
    },
  },
};
</script>

<style>
.parallax-bg {
  /* The image used */
  background-image: var(--background-image);

  background-size: contain;

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: var(--background-position);
  background-repeat: no-repeat;
  background-size: cover;
}
</style>