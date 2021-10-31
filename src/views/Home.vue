<template>
  <!-- <div > -->
  <v-card width="100%"  class=".text-caption" dark id="fondo-img">
    <portafolio />
    <!-- <hr> -->
    <skillset />
    <!-- <hr> -->
    <experiencia />
    <!-- <hr> -->
    <footer-portafolio />
  </v-card>
</template>

<script>
import Experiencia from "../components/Experiencia.vue";
import FooterPortafolio from "../components/FooterPortafolio.vue";
import Portafolio from "../components/portafolio.vue";
import Skillset from "../components/Skillset.vue";

export default {
  name: "Home",

  components: {
    Portafolio,
    FooterPortafolio,
    Skillset,
    Experiencia,
  },
};
</script>

<style>
#fondo-img {
  background-image: url("../assets/img_programming.png");
  background-position: center, center !important;
  background-size: cover !important ;
  height: 100%;
}
</style>
