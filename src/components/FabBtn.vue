<template>
  <v-btn
    elevation="2"
    fab
    fixed
    right
    bottom
    color="primary"
    @click="fabScrollNext()"
  >
    <v-icon v-if="nextSectionIndex == 0">mdi-arrow-up</v-icon>
    <v-icon v-else>mdi-arrow-down</v-icon>
  </v-btn>
</template>

<script>
export default {
  name: "FabBtn",
  props: {
    navList: {
      type: Array,
      required: true,
    },
    currentScroll: {
      type: Number,
      required: true,
    },
    scrollSection: {
      type: Function,
      required: true,
    },
  },
  methods: {
    fabScrollNext() {
      // Scroll to next section
      this.scrollSection(this.nextSectionId);
    },
  },
  computed: {
    sectionPositionList() {
      // 0,0,995,2655,3002
      return this.navList.map((item) => {
        return document.getElementById(item.section_id).offsetTop;
      });
    },
    currentSectionId() {
      // Get current section id
      return this.navList.find((item, index) => {
        // Return last section if index is last
        if (index === this.navList.length - 1) {
          return true;
        }
        // Return section if currentScroll is between section positions
        return (
          this.currentScroll >=
            document.getElementById(item.section_id).offsetTop &&
          this.currentScroll <
            document.getElementById(this.navList[index + 1].section_id)
              .offsetTop
        );
      }).section_id;
    },
    currentSectionIndex() {
      // Get current section index
      return this.navList.findIndex((item) => {
        return item.section_id === this.currentSectionId;
      });
    },
    nextSectionIndex() {
      // Get next section index
      // If reach last section, scroll to top
      return this.currentSectionIndex === this.navList.length - 1
        ? 0
        : this.currentSectionIndex + 1;
    },
    nextSectionId() {
      // Get next section id
      return this.navList[this.nextSectionIndex].section_id;
    },
  },
};
</script>

<style>
</style>