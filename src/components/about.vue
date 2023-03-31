<template>
  <div id="about">
    <v-container>
      <v-row>
        <v-col cols="12" sm="6" class="d-flex justify-center">
          <v-tooltip text="Hello ! 😁" >
                  <template v-slot:activator="{ props }">
                    <v-img src="../assets/mehdidissem.png" v-bind="props" max-width="400px" contain class="image-effect"></v-img>
                  </template>
                </v-tooltip>
        </v-col>
        <v-col cols="12" sm="5">
          <h2>ABOUT ME</h2>
          <p>
            As a Full Stack web developer, I possess a strong commitment to excellence, a collaborative mindset, and effective communication skills.
          </p>
          <p>
            Drawing upon six years of experience across diverse marketing fields, including article writing, SEO, freelancing, and market analysis, I have honed a versatile set of technical and non-technical skills.
          </p>
          <!-- <p>
            I am now seeking new opportunities in the IT field to further enhance my technical abilities and contribute to innovative projects.
          </p> -->
          <div>
            <h2>Certifications</h2>
            <h4 class="creds">Click on the certification to show credential</h4>
            <certifications style="background-color: transparent;"></certifications>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
  <div class="articles" style="text-align: center;">
    <h3 class="article-header">My Articles on <span @click="openMedium" class="medium-link">Medium</span></h3> <p class="notice">(click on the title to go to my Medium profile)</p>
    <iframe src='https://widgets.sociablekit.com/medium-publication-feed/iframe/123402' frameborder='0' width='85%' height='500' style="border:10cap; margin: 10px auto; display:relative;"></iframe>
  </div>
</template>

<script>
import certifications from "./certifications.vue"
export default {
  name: 'about',
  components: {
    'certifications': certifications
  },
  methods:{
    openMedium() {
      window.open('https://medium.com/@mehdissem', '_blank');
    }
  }
};
</script>

<style lang="scss" scoped>
#about {
  padding: 25px;
  background-color: #1A1A1D;
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
    // color: var(--gray);
    color:white;
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

// .image-effect::after {
//   content: "";
//   position: absolute;
//   top: 50%;
//   left: 50%;
//   transform: translate(-50%, -50%) scale(0);
//   width: 0;
//   height: 0;
//   border-radius: 50%;
//   background: rgba(255, 255, 255, 0.2);
//   transition: all 0.3s ease-out;
//   pointer-events: none;
// }

.image-effect:hover img {
  transform: scale(1.1);
}

.image-effect:hover::after {
  transform: translate(-50%, -50%) scale(3);
  width: 200%;
  height: 200%;
}

.articles{
  margin:50px;
  margin-bottom: 10px;
}
.article-header {
  display: inline-block;
  position: relative;
  padding-top: 15px;
  font-size: 1.5rem;
  text-transform: uppercase;
    font-weight: bold;
    color: var(--accent-color);
}

.article-header::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: var(--accent-color);
  transform: scaleX(0);
  transform-origin: bottom right;
  transition: transform 0.3s ease-out;
}

.article-header:hover::after {
  transform-origin: bottom left;
  transform: scaleX(1);
}

.notice{
  margin-top: 15px;
  font-size: 13px;
}
.notice:hover{
  animation:shake 0.82s cubic-bezier(.36,.07,.19,.97) both;
}

@keyframes shake {
  10%, 90% {
    transform: translate3d(-1px, 0, 0);
  }
  
  20%, 80% {
    transform: translate3d(2px, 0, 0);
  }

  30%, 50%, 70% {
    transform: translate3d(-4px, 0, 0);
  }

  40%, 60% {
    transform: translate3d(4px, 0, 0);
  }
}

@media screen and (max-width: 768px)  {
  .articles{
    margin:0px;
    margin-bottom: 30px;
}
}
.creds{
  font-size: 14px;
  color:white;
  animation: shake 0.5s ease-in-out 3s;
}
.creds:hover{
  animation:shake 0.5s ease-in-out 3s
}

@keyframes shake {
  0% { transform: translate(0, 0); }
  25% { transform: translate(-5px, 5px); }
  50% { transform: translate(5px, -5px); }
  75% { transform: translate(5px, 5px); }
  100% { transform: translate(-5px, -5px); }
}
</style>
