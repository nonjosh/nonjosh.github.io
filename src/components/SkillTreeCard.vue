<template>
  <v-card class="mx-auto" max-width="500">
    <v-sheet class="pa-4 lighten-2">
      <v-text-field
        v-model="search"
        label="Search My Skills Here!"
        dark
        flat
        solo-inverted
        hide-details
        clearable
        clear-icon="mdi-close-circle-outline"
      ></v-text-field>
      <v-checkbox
        v-model="caseSensitive"
        dark
        hide-details
        label="Case sensitive search"
      ></v-checkbox>
    </v-sheet>
    <v-card-text class="text-left">
      <v-treeview
        :items="items"
        :search="search"
        :filter="filter"
        :open.sync="open"
      >
        <template v-slot:prepend="{ item }">
          <v-icon v-if="item.children">mdi-folder-network</v-icon>
          <v-icon v-else>mdi-code-tags</v-icon>
        </template>
      </v-treeview>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "SkillTreeCard",
  data: () => ({
    items: [
      {
        id: 1,
        name: "Frontend",
        children: [
          {
            id: 10,
            name: "⭐VueJS",
            children: [
              {
                id: 101,
                name: "Vuetify",
              },
              {
                id: 102,
                name: "NuxtJS",
              },
            ],
          },
        ],
      },
      {
        id: 2,
        name: "Backend",
        children: [
          {
            id: 20,
            name: "⭐Python",
            children: [
              {
                id: 201,
                name: "flask",
              },
              {
                id: 202,
                name: "fastapi",
              },
            ],
          },
          {
            id: 21,
            name: "Java",
            children: [{ id: 211, name: "Spring" }],
          },
          {
            id: 22,
            name: "Go",
            children: [{ id: 221, name: "Echo" }],
          },
          {
            id: 23,
            name: "NodeJS",
            children: [{ id: 231, name: "ExpressJS" }],
          },
        ],
      },
      {
        id: 4,
        name: "Database",
        children: [
          {
            id: 40,
            name: "⭐RDBMS",
            children: [
              {
                id: 401,
                name: "Oracle",
              },
              {
                id: 402,
                name: "MySQL",
              },
              {
                id: 403,
                name: "SQLite",
              },
              {
                id: 404,
                name: "PostgreSQL",
              },
            ],
          },
          {
            id: 41,
            name: "NoSQL",
            children: [{ id: 411, name: "MongoDB" }],
          },
          {
            id: 42,
            name: "MinIO",
          },
        ],
      },
      {
        id: 3,
        name: "Intrastructure and others",
        children: [
          {
            id: 30,
            name: "IaC",
            children: [
              {
                id: 301,
                name: "Ansible",
              },
              {
                id: 302,
                name: "Terraform",
              },
            ],
          },
          {
            id: 31,
            name: "Docker",
          },
          {
            id: 32,
            name: "Kubernetes",
          },
          {
            id: 33,
            name: "Web Servers",
            children: [
              {
                id: 331,
                name: "Nginx",
              },
              {
                id: 332,
                name: "Apache",
              },
              {
                id: 333,
                name: "IIS",
              },
            ],
          },
        ],
      },
    ],
    open: [1, 2],
    search: null,
    caseSensitive: false,
  }),
  computed: {
    filter() {
      return this.caseSensitive
        ? (item, search, textKey) => item[textKey].indexOf(search) > -1
        : undefined;
    },
  },
};
</script>

<style>
</style>