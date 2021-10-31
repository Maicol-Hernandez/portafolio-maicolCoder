<template>
  <v-app>
    <!-- <v-card dark class="overflow-hidden"> -->
    <v-app-bar
      app
      src="./assets/img_programming.png"
      height="90"
      elevation="20"
      dark
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(19,84,15,.8)"
        >
        </v-img>
      </template>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-app-bar-title
      class=".text-caption"
        >Maicol Hernandez Peralta

        <p class="subtitle-1">Desarrollador Web</p>
      </v-app-bar-title>

      <v-spacer></v-spacer>
      <!-- <v-btn icon class="mr-3" @click="modoOscuro" v-model="darkMode">
          <v-icon>mdi-theme-light-dark</v-icon>
        </v-btn> -->
      <div class="mb-1">
        <v-menu bottom rounded max-width="200px" offset-y>
          <template v-slot:activator="{ on }">
            <v-btn icon x-large v-on="on">
              <v-avatar size="70">
                <v-img :src="user.foto"></v-img>
              </v-avatar>
            </v-btn>
          </template>
          <v-card elevation="1">
            <v-list-item-content class="justify-center">
              <div class="mx-auto text-center">
                <v-avatar>
                  <v-img :src="user.foto"></v-img>
                </v-avatar>

                <h3>{{ user.nombreCompleto }}</h3>
                <p class="text-caption mt-1">{{ user.email }}</p>

                <v-divider class="my-3"></v-divider>
                <v-btn depressed rounded text> Contactarme </v-btn>
                <v-divider class="my-3"></v-divider>
                <v-btn depressed rounded text> Email </v-btn>
              </div>
            </v-list-item-content>
          </v-card>
        </v-menu>
      </div>
    </v-app-bar>
    <v-main>
      <router-view />
    </v-main>
    <!-- </v-card> -->
  </v-app>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    user: {
      foto: require("@/assets/avatar_maicol.jpeg"),
      email: "maicolhernandez420@gmail.com",
      nombreCompleto: "Maicol Fernando Hernandez Peralta",
      urlImg: require("@/assets/img_programming.jpg"),
      profesion: "Tecnologo/Analisis y Desarrollo de Sistemas de Informacion",
    },
    // darkMode: "",
  }),
  watch: {
    // darkMode: function (val) {
    //   console.log(val);
    // },
  },
  methods: {
    // modoOscuro: function (val) {
    //   console.log(val);
    //   return "red";
    // },
  },
};
</script>