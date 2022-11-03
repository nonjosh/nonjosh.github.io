<template>
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
</template>

<script>
export default {
  name: "ShowcaseCard",
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  methods: {
    showPreview(imgSrc) {
      this.$emit("showPreview", imgSrc);
    },
  },
};
</script>

<style>
</style>