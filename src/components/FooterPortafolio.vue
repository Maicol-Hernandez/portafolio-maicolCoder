<template>
  <v-footer dark color="rgba(12, 155, 155, 0.3)" width="100%" padless>
    <v-card
      tile
      flat
      width="100%"
      color="rgba(12, 155, 122, 0.1)"
      class="white--text text-center"
    >
      <v-card-title
        class="
          white--text
          font-weigth-bold
          text-uppercase text-h4
          justify-center
        "
      >
        <strong>Contactame</strong>
      </v-card-title>

      <v-card-text>
        <v-tooltip v-for="icon in icons" :key="icon.id" bottom>
          <template v-slot:activator="{ on, attrs }">
            <a :href="icon.link">
            <v-btn  v-on="on" v-bind="attrs" class="mx-4 white--text" icon>
              <v-icon  size="24px">
                  
              
                {{ icon.icon }}
              </v-icon>
            </v-btn>        
                  </a>
            
          </template>
          <span>{{ icon.name }}</span>
        </v-tooltip>
      </v-card-text>

      <v-form>
        <v-card-text class="white--text pt-0">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum minus
          mollitia magnam vel hic quae exercitationem odit placeat. Earum cumque
          eum pariatur officiis nobis cum harum a eveniet reiciendis mollitia.
          Lorem ipsum dolor, sit amet consectetur adipisicing elit.
          <v-row class="mt-4" dense justify="center">
            <v-col cols="12" md="5" lg="4">
              <v-text-field dense label="Nombres"></v-text-field>
              <v-text-field dense label="Apellidos"></v-text-field>
              <v-text-field dense label="E-mail"> </v-text-field>
            </v-col>
            <v-col cols="12" md="4" lg="4" align-self="end">
              <v-textarea
                outlined
                class="mt-5"
                auto-grow
                row-height="20"
                dense
                label="Nota"
                shaped
              ></v-textarea>
              <v-row
                dense
                justify-lg="end"
                justify-sm="center"
                justify-md="end"
              >
                <v-btn>Enviar</v-btn>
              </v-row>
            </v-col>
          </v-row>
        </v-card-text>
      </v-form>
      <v-divider></v-divider>
      <v-card-text class="py-2 white--text" id="footer">
        Desarrollado y diseñado por Michael Fernando Hernandez Peralta. &copy;{{
          new Date().getFullYear()
        }}. Todos los derechos reservados
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "FooterPortafolio",
  data: () => ({
    icons: [
      { id: 1, icon: "mdi-github", name: "GitHub", link: "https://github.com/Maicol-Hernandez" },
      { id: 2, icon: "mdi-linkedin", name: "Linkedin" },
      { id: 3, icon: "mdi-facebook", name: "Facebook", },
    ],
  }),
};
</script>

<style>
#footer {
  font: caption;
  letter-spacing: 0.0333333333em;
  font-weight: 400;
  /* background-color: #424242; */
  font-size: 0.75rem;
}

/* 
      <v-card-text>
        <v-row class="red" justify="center" dense>
          <v-col
            cols="12"
            lg="1"
            class="warning"
            v-for="icon of icons"
            :key="icon.id"
          >
            <v-tooltip bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-btn v-on="on" v-bind="attrs" class="mx-4 white--text" icon>
                  <v-icon size="24px">
                    {{ icon.icon }}
                  </v-icon>
                </v-btn>
              </template>
              {{ icon.name }}
            </v-tooltip>
          </v-col>
        </v-row>

      </v-card-text> */
</style>