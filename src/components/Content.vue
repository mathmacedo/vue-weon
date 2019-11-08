
<template>
  <div style="width: 100%" class="d-inline-flex">
    <div class="grey darken-1" style="width: 15%">
      <v-row>
        <v-col></v-col>
      </v-row>
    </div>
    <div class="grey darken-3" style="width: 85%">
      <div style="width: 85%">
        <v-tabs background-color="grey darken-3" dark>
          <v-tab>MONITOR</v-tab>
          <v-tab>GRÁFICO</v-tab>
          <v-tab>ATENDIMENTOS</v-tab>
        </v-tabs>

        <v-row class="my-3 mx-3">
          <v-col>
            <span style="color: white" class="mr-2">{{this.statusDisponivel}}</span>
            <span style="color: white" class="mr-2">Disponível</span>
            <v-progress-linear
              color="green lighten-1"
              v-model="statusDisponivel"
              background-color="green darken-1"
            ></v-progress-linear>
          </v-col>
          <v-col>
            <span style="color: white" class="mr-2">{{this.statusAtendendo}}</span>
            <span style="color: white" class="mr-2">Atendendo</span>
            <v-progress-linear
              color="red lighten-1"
              v-model="statusAtendendo"
              background-color="red darken-1"
            ></v-progress-linear>
          </v-col>
          <v-col>
            <span style="color: white" class="mr-2">{{this.statusPausa}}</span>
            <span style="color: white" class="mr-2">Pausa</span>
            <v-progress-linear
              color="yellow lighten-1"
              v-model="statusPausa"
              background-color="yellow darken-1"
            ></v-progress-linear>
          </v-col>
          <v-col>
            <span style="color: white" class="mr-2">{{this.statusDesconectado}}</span>
            <span style="color: white" class="mr-2">Desconectado</span>
            <v-progress-linear
              color="grey lighten-1"
              v-model="statusDesconectado"
              background-color="grey darken-1"
            ></v-progress-linear>
          </v-col>
        </v-row>

        <v-data-table
          :headers="headers"
          :items="data_json[0].members"
          show-select
          fixed-header
          disable-sort
          hide-default-footer
          class="elevation-1"
        >
          <template slot="items" slot-scope="props">
            <tr style="background-color: red" :key="props.index">
              <td>{{ props.item.name }}</td>
              <td>{{ props.item.id }}</td>
              <td>{{ props.item.status }}</td>
              <td>{{ props.item.time }}</td>
              <td>{{ props.item.quantidade }}</td>
            </tr>
          </template>
        </v-data-table>
      </div>
    </div>
  </div>
</template>

<script>
import data_json from "../json/data.json";

export default {
  name: "Content",

  data() {
    return {
      selected: [],
      statusDisponivel: null,
      statusAtendendo: null,
      statusPausa: null,
      statusDesconectado: null,
      data_json: data_json,
      headers: [
        { text: "Nome", value: "name" },
        { text: "Id", value: "id" },
        { text: "Status", value: "status" },
        { text: "Tempo", value: "time" },
        { text: "Qtde", value: "quantidade" }
      ]
    };
  },
  methods: {
    getColor(status) {
      if (status == "Disponível") {
        return "green";
      } else if (status == "Pausa (Almoço)") {
        return "yellow";
      } else if (status == "Desconectado") {
        return "grey";
      } else {
        return "red";
      }
    },

    defineNumberStatus() {
      var disponivel = 0;
      var atendendo = 0;
      var pausa = 0;
      var desconectado = 0;
      for (var i in data_json[0].members) {
        if (data_json[0].members[i].status == "Disponível") {
          disponivel++;
        } else if (data_json[0].members[i].status == "Pausa (Almoço)") {
          pausa++;
        } else if (data_json[0].members[i].status == "Desconectado") {
          desconectado++;
        } else {
          atendendo++;
        }
      }

      this.$data.statusDisponivel = disponivel;
      this.$data.statusAtendendo = atendendo;
      this.$data.statusPausa = pausa;
      this.$data.statusDesconectado = desconectado;
    }
  },

  beforeMount() {
    this.defineNumberStatus();
  }
};
</script>