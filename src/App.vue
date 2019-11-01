<template>
  <v-app>
    <v-content>
      <NavigationMenu />
    </v-content>
  </v-app>
</template>

<script>
import NavigationMenu from "./components/NavigationMenu";

export default {
  name: "App",
  components: {
    NavigationMenu
  },
  data: () => ({
    //
  })
};
</script>
