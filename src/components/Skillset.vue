<template>
  <v-container fluid>
    <!-- <v-card  flat tile width="100%" class="text-center"> -->
    <v-row class="mb-1" >
      <v-col cols="12" lg="12" >
        <v-card-title
          class="
            white--text
            font-weigth-bold
            text-uppercase text-h4
            justify-center
          "
        >
          <strong>skillset</strong>
        </v-card-title>
        <hr class="mb-5" />
        <v-card-text>
          <v-row dense justify="start">
            <v-col
              v-for="img in imgsExperiencia"
              :key="img.id"
              cols="6"
              lg="3"
              md="3"
              sm="4"
            >
              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }">
                  <v-row dense justify="center" class="my-2">
                    <v-avatar
                      v-on="on"
                      v-bind="attrs"
                      rounded
                      size="110"
                      class="color-avatar"
                    >
                      <v-img :src="img.foto"> </v-img>
                    </v-avatar>
                  </v-row>
                </template>
                <span>{{ img.nombre }}</span>
              </v-tooltip>
            </v-col>
          </v-row>
        </v-card-text>
      </v-col>
    </v-row>
    <!-- </v-card> -->
  </v-container>
</template>

<script>
export default {
  name: "Skillset",
  data: () => ({
    imgsExperiencia: [
      {
        id: 1,
        nombre: "Angular",
        foto: require("@/assets/Angularjs.png"),
      },
      { id: 2, nombre: "CSS", foto: require("@/assets/CSS.png") },
      { is: 3, nombre: "Javascript", foto: require("@/assets/Javascript.png") },
      {
        id: 4,
        nombre: "Mysql Workbech",
        foto: require("@/assets/mysql_workbench.png"),
      },
      { id: 5, nombre: "Python", foto: require("@/assets/python.png") },
      { id: 6, nombre: "Vue2.js", foto: require("@/assets/vue2.png") },
      { id: 7, nombre: "Vuetify", foto: require("@/assets/vuetify.png") },
      { id: 8, nombre: "HTML", foto: require("@/assets/HTML.png") },
      { id: 9, nombre: "HTML", foto: require("@/assets/HTML.png") },
      { id: 10, nombre: "HTML", foto: require("@/assets/HTML.png") },
    ],
  }),
};
</script>

<style >
.color-avatar {
  background: white;
  /* background: -webkit-linear-gradient(to right, #f09819, #ff512f);
  background: linear-gradient(to right, #f09819, #ff512f); */
}
.color-skills {
  background: #00b0c7;
}
</style>
