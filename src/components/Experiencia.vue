<template>
  <v-container fluid>
    <v-card-title
      class="white--text font-weigth-bold text-uppercase text-h4 justify-center"
    >
      <strong>Experiencia</strong>
    </v-card-title>
    <hr class="mb-5" />
    <v-card-text>
      <v-row dense justify="center">
        <v-col cols="12" lg="7">
          <v-row dense id="boder-content">
            <v-col
              cols="12"
              lg="6"
              v-for="n of 6"
              :key="n"
              class="d-flex child-flex"
            >
              <v-hover close-delay="200" open-delay="200">
                <template v-slot:default="{ hover }">
                  <v-card
                    id="hover"
                    :elevation="hover ? 12 : 2"
                    :class="{ 'on-hover': hover }"
                  >
                    <v-img
                      contain
                      :src="`https://picsum.photos/500/300?image=${
                        n + 160 + 9
                      }`"
                      :lazy-src="`https://picsum.photos/10/6?image=${
                        n * 5 + 10
                      }`"
                      aspect-ratio="2"
                      max-height="200"
                      class="grey darken-4"
                    >
                      <template v-slot:placeholder>
                        <v-row
                          dense
                          class="fill-height ma-0"
                          justify="center"
                          align="center"
                        >
                          <v-progress-circular
                            color="grey lighten-5"
                            indeterminate
                          ></v-progress-circular>
                        </v-row>
                      </template>
                    </v-img>
                    <v-fab-transition>
                      <v-overlay v-show="hover" absolute color="info lighten-3">
                        <v-btn @click="activateDialog(true)" dark icon>
                          <v-icon x-large color="secondary darken-4" dark
                            >mdi-magnify</v-icon
                          >
                        </v-btn>
                      </v-overlay>
                    </v-fab-transition>
                  </v-card>
                </template>
              </v-hover>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
      <v-dialog
        dark
        v-model="dialog"
        :max-width="maxWidth"
        transition="dialog-transition"
        persistent
      >
        <v-card>
          <v-card-title primary-title class="headline" id="color-modal">
            <v-icon class="mr-2"> mdi-briefcase-search-outline </v-icon>
            Experiencia
          </v-card-title>
          <v-card-text class="pb-0">
            <v-chip
              text-color="white"
              label
              color="cyan darken-4"
              draggable
              class="my-3"
              ><v-avatar class="mr-1" >
                <v-icon>mdi-briefcase</v-icon>
              </v-avatar>
              Nombre mepresa</v-chip
            >
            <p class="text-justify">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Est
              aperiam animi rem doloribus laudantium vel optio odio impedit
              possimus laboriosam laborum accusamus, beatae aliquid fugit
              dignissimos at ducimus nisi officiis?
            </p>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn outlined text @click="dialog = false">Cerrar</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-card-text>
  </v-container>
</template>

<script>
export default {
  name: "Experiencia",
  data: () => ({
    dialog: false,
    maxWidth: 500,
  }),

  methods: {
    activateDialog: function (estado) {
      console.log(estado);
      this.dialog = estado;
    },
  },
};
</script>
<style scoped>
#hover {
  border: 4px solid #00b0c7;
  transition: opacity 0.6s ease-in-out;
}
#hover:not(.on-hover) {
  opacity: 0.8;
  border-radius: 25px;
}
#color-modal {
  background: linear-gradient(
    to right,
    rgba(19, 84, 122, 0.5),
    rgba(19, 84, 15, 0.8)
  );
}
</style>