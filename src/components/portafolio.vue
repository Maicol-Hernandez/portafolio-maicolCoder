<template>
  <v-container fluid class="text-center">
    
    <p
      class="text-h4 justify-center text-uppercase font-weigth-bold white--text"
    >
      <strong>Portafolio</strong>
    </p>
    <hr class="mb-5" />
    
    <div v-for="card in 4" :key="card">
      <v-hover>
        <template v-slot:default="{ hover }">
          <v-card class="mx-auto mb-10" height="270" max-width="500" tile>
            <v-img height="100%" :src="user.urlImg">
              <v-row align="end" class="fill-height">
                <v-col cols="12" lg="12" align-self="start" class="pa-0">
                  <v-avatar
                    class="pt-4  profile"
                    dark
                    width="100%"
                    size="199"
                    tile
                  >
                    <v-img  max-width="90%" max-height="90%"  :src="user.foto"></v-img>
                  </v-avatar>
                </v-col>
                <v-col cols="12" lg="12" class="py-0">
                <v-card-text  class="  ">
                  
                    <v-list-item>
                      <v-list-item-content>
                        <v-list-item-title>
                          {{ user.nombreCompleto }}
                        </v-list-item-title>
                        <v-list-item-subtitle  >
                          {{ user.profesion }}
                        </v-list-item-subtitle>
                      </v-list-item-content>
                    </v-list-item>
                </v-card-text>
                  </v-col>
                
              </v-row>
            </v-img>

            <v-fade-transition>
              <v-overlay v-show="hover" absolute color="#036358">
                <v-btn dark block>ver mas</v-btn>
              </v-overlay>
            </v-fade-transition>
          </v-card>
        </template>
      </v-hover>
    </div>

  </v-container>
</template>

<script>
export default {
  name: "portafolio",
  data: () => ({
    user: {
      foto: require("../assets/img-card.jpg"),
      nombreCompleto: "Maicol Fernando Hernandez Peralta",
      urlImg: require("@/assets/img_programming.jpg"),
      profesion: "Tecnologo / Analisis y Desarrollo de Sistemas de Informacion",
    },
  }),
};
</script>
