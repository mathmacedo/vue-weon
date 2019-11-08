
<template>
  <div>
    <v-app-bar color="black" height="70">
      <v-row>
        <v-col md="2" class="align-self-center">
          <v-img src="../assets/weon.png" width="145px" height="50px"></v-img>
        </v-col>
        <v-col md="4" offset="2" class="d-flex justify-center" align-self="center">
          <v-text-field
            label="Buscar Contato"
            dark
            solo-inverted
            flat
            prepend-inner-icon="mdi-magnify"
          ></v-text-field>
          <v-icon class="ml-4" color="rgb(96, 96, 96)">mdi-account-plus</v-icon>
        </v-col>
        <v-col md="2" offset="2" class="d-flex justify-center align-self-center">
          <v-icon color="rgb(96, 96, 96)">forum</v-icon>
          <v-avatar color="indigo" size="38" class="ml-10 mr-3">
            <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
          </v-avatar>
          <div class="d-flex flex-column align-self-center" style="text-align: center">
            <span style="font-size: 14px; color: white">Supervisor</span>
            <span style="font-size: 14px; color: white;">supisolve</span>
          </div>
        </v-col>
      </v-row>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "NavigationHeader",

  data: () => ({})
};
</script>
