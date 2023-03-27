<template>
    <v-card elevation="24" max-width="444" class="mx-auto">
      <v-carousel
        :continuous="false"
        :show-arrows="false"
        hide-delimiter-background
        delimiter-icon="mdi-square"
        height="300"
      >
        <v-carousel-item v-for="(slide, i) in myCertifications" :key="i">
          <v-sheet height="100%" tile>
            <div class="d-flex fill-height justify-center align-center">
              <v-tooltip bottom>
                <template v-slot:activator="{ on }">
                  <img v-bind:src="slide.image" v-on="on" />
                </template>
                <span>{{ slide.certificateURL }}</span>
              </v-tooltip>
            </div>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </v-card>
  </template>
  
  <script>
  import myCertifications from "@/store/certifications";
  
  export default {
    name: "Certifications",
    data() {
      return {
        myCertifications,
      };
    },
  };
  </script>
  
  <style scoped>
  </style>
  