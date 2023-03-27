<template>
    <v-carousel
      cycle
      height="370"
      hide-delimiters=""
      show-arrows="hover"
      class="carousel"
    >
      <v-carousel-item v-for="(certification, i) in myCertifications" :key="i">
        <v-sheet height="100%" color="transparent">
          <div class="d-flex fill-height justify-center align-center">
            <a :href="certification.certificateURL" target="_blank">
              <img
                :src="certification.image"
                alt="Certification Image"
                class="certification-image"
              />
            </a>
          </div>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
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
  .certification-image {
    max-width: 60%;
    max-height: 60%;
    object-fit: contain;
    margin: auto;
    display: block;
    transition: transform 0.2s ease-in-out;
    transition-delay: 3s;
  }
  
  @media screen and (max-width: 600px) {
    .certification-image {
      max-width: 100%;
      max-height: 100%;
    }
  }
  
  .certification-image:hover {
    transform: scale(1.8);
    z-index: 9999;
  }
  
  @media screen and (max-width: 768px) {
    .certification-image {
      max-width: 100%;
      max-height: 100%;
    }
  }
  
  @media screen and (max-width: 1024px) {
    .certification-image {
      width:100%;
      height: 100%;
    }
  }
  </style>
  