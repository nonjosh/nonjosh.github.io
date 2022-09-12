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
          <v-icon v-if="item.icon">{{ item.icon }}</v-icon>
          <v-icon v-else> mdi-code-tags </v-icon>
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
        icon: "mdi-web",
        children: [
          {
            id: 10,
            name: "⭐VueJS",
            icon: "mdi-vuejs",
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
        icon: "mdi-server",
        children: [
          {
            id: 20,
            name: "⭐Python",
            icon: "mdi-language-python",
            children: [
              {
                id: 201,
                name: "flask",
              },
              {
                id: 202,
                name: "fastapi",
              },
              {
                id: 203,
                name: "tensorflow",
                icon: "mdi-robot",
              },
            ],
          },
          {
            id: 21,
            name: "Java",
            icon: "mdi-language-java",
            children: [{ id: 211, name: "Spring" }],
          },
          {
            id: 22,
            name: "Go",
            icon: "mdi-language-go",
            children: [{ id: 221, name: "Echo" }],
          },
          {
            id: 23,
            name: "NodeJS",
            icon: "mdi-language-javascript",
            children: [{ id: 231, name: "ExpressJS" }],
          },
        ],
      },
      {
        id: 4,
        name: "Database",
        icon: "mdi-database",
        children: [
          {
            id: 40,
            name: "⭐RDBMS",
            icon: "mdi-folder",
            children: [
              {
                id: 401,
                name: "Oracle",
                icon: "mdi-database",
              },
              {
                id: 402,
                name: "MySQL",
                icon: "mdi-database",
              },
              {
                id: 403,
                name: "SQLite",
                icon: "mdi-database",
              },
              {
                id: 404,
                name: "PostgreSQL",
                icon: "mdi-database",
              },
            ],
          },
          {
            id: 41,
            name: "NoSQL",
            icon: "mdi-folder",
            children: [{ id: 411, name: "MongoDB", icon: "mdi-database" }],
          },
          {
            id: 42,
            name: "MinIO",
            icon: "mdi-database",
          },
        ],
      },
      {
        id: 3,
        name: "Intrastructure and others",
        icon: "mdi-server-network",
        children: [
          {
            id: 30,
            name: "IaC",
            icon: "mdi-folder",
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
            icon: "mdi-docker",
          },
          {
            id: 32,
            name: "Kubernetes",
            icon: "mdi-kubernetes",
          },
          {
            id: 33,
            name: "Web Servers",
            icon: "mdi-server-network",
            children: [
              {
                id: 331,
                name: "Nginx",
                icon: "mdi-server-network",
              },
              {
                id: 332,
                name: "Apache",
                icon: "mdi-server-network",
              },
              {
                id: 333,
                name: "IIS",
                icon: "mdi-server-network",
              },
            ],
          },
        ],
      },
    ],
    open: [2, 3, 4],
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