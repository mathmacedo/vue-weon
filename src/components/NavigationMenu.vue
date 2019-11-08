<template>
  <v-card width="10%" height="100%">
    <v-navigation-drawer permanent dark>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>Dashboard</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>Painel</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-list dense nav>
        <v-list-item v-for="item in items2" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>Admin</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-list dense nav>
        <v-list-item v-for="item in items3" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: "Atendentes", icon: "mdi-view-dashboard" },
      { title: "Geral", icon: "mdi-view-dashboard" },
      { title: "Filas Principais", icon: "mdi-view-dashboard" }
    ],
    items2: [
      { title: "Filas", icon: "mdi-view-dashboard" },
      { title: "Campanhas", icon: "mdi-view-dashboard" },
      { title: "Agentes", icon: "mdi-view-dashboard" }
    ],
    items3: [
      { title: "Agentes", icon: "mdi-view-dashboard" },
      { title: "Filas", icon: "mdi-view-dashboard" },
      { title: "Campanhas", icon: "mdi-view-dashboard" },
      { title: "Discadores", icon: "mdi-view-dashboard" }
    ],
    right: null
  })
};
</script>
