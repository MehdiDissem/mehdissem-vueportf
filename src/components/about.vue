<template>
    <div id="about">
      <v-container>
        <v-row>
            <v-col cols="12" sm="6" class="d-flex justify-center">
  <v-img src="../assets/mehdidissem.png" max-width="400px" contain class="image-effect"></v-img>
</v-col>
          <v-col cols="12" sm="6">
            <h2>ABOUT ME</h2>
            <p>
              As a Full Stack web developer, I possess a strong commitment to excellence, a collaborative mindset, and effective communication skills.
            </p>
            <p>
              Drawing upon six years of experience across diverse marketing fields, including article writing, SEO, freelancing, and market analysis, I have honed a versatile set of technical and non-technical skills.
            </p>
            <p>
              I am now seeking new opportunities in the IT field to further enhance my technical abilities and contribute to innovative projects.
            </p>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </template>
  
  <script>
  export default {
    name: 'about',
  };
  </script>
  
  <style lang="scss" scoped>
  #about {
    padding: 15px;
    h2 {
      text-transform: uppercase;
      font-weight: bold;
      color: var(--accent-color);
      padding-top: 15px;
      font-size: 1.5rem;
    }
    p {
      padding-block: 10px;
      padding-right: 10px;
      font-weight: 400;
      color: var(--gray);
      font-size: 1.5rem;
    }
  }
  .image-effect {
    position: relative;
    overflow: hidden;
  }

  .image-effect img {
    transition: all 0.3s ease-out;
  }

  .image-effect:hover img {
    transform: scale(1.2);
  }

  .image-effect::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0;
    background: rgba(0, 0, 0, 0.5);
    transition: all 0.3s ease-out;
    pointer-events: none;
  }

  .image-effect:hover::before {
    opacity: 1;
  }
  </style>
  