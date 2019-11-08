<template>
  <v-app>
    <NavigationHeader />
    <div class="d-inline-flex" style="height: 100%">
      <NavigationMenu />
      <Content />
    </div>
  </v-app>
</template>


<script>
import NavigationHeader from "./components/NavigationHeader";
import NavigationMenu from "./components/NavigationMenu";
import Content from "./components/Content";

export default {
  name: "App",
  components: {
    NavigationMenu,
    NavigationHeader,
    Content
  },
  data: () => ({
    //
  })
};
</script>
