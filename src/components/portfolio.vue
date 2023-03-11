<template>
  <v-container fluid class="ma-0 portfolio" id="portfolio">
    <h2 class="">Portfolio</h2>
    <v-container fluid class="projects pa-0 pa-md-4">
          <v-row align="center" justify="center" class="mx-0" no-gutters>
          <v-col cols="12" md="6" lg="4" v-for="(project, index) in myProjects" :key="index">
            <v-hover v-slot="{ hover }">
              <v-card class="mb-4 grey project" elevation="2" height="100%" :rounded="hover" :href="project.link" target="_blank">
                <v-img
                  :src="project.picture"
                  max-height="100%"
                  class="d-flex align-center justify-center"
                  :class="{ 'grey lighten-3': !hover }"
                >
                  <v-expand-transition>
                    <div
                      v-if="hover"
                      class="d-flex flex-column transition-fast-in-fast-out red darken-2 v-card--reveal white--text pa-3 justify-center align-center card-reveal"
                    >
                      <span class="my-2 mono" id="project_name">{{ project.title }}</span>
                      <span class="montserrat description">{{ project.description }}</span>
                      <v-btn flat :href="project.link" target="_blank" tile width="50%" class="mx-auto my-1 mt-2">Visit</v-btn>
                      <div class="tech-icons d-flex flex-row flex-wrap" width="100%">
                        <v-img
                          :src="icon_path(tech)"
                          v-for="(tech, techIndex) in project.technologiesUsed.split(',')"
                          :key="techIndex"
                          width="30px"
                          height="30px"
                          contain
                          class="mx-2"
                          id="tech-icon"
                        ></v-img>
                      </div>
                    </div>
                  </v-expand-transition>
                </v-img>
                <div class="pa-3">
                  <span class="montserrat">{{ project.description }}</span>
                </div>
              </v-card>
            </v-hover>
          </v-col>
        </v-row>
    </v-container>

      <h1 class="display-2 text-center mt-5 animated fadeIn delay-1s">
        <a href="https://github.com/MehdiDissem" target="_blank" class="github-link">

          <span>
            Check out my GitHub for even more!
          </span>
          <svg viewBox="0 0 260 60" xmlns="http://www.w3.org/2000/svg">
      <path d="M1,30 Q70,40 130,30 Q190,20 250,30" stroke="#950740" stroke-width="5" fill="none" stroke-dasharray="10,10"/>
    </svg>
        </a>
      </h1>

</v-container>
</template>

<script>
import myProjects from "../store/index.js"
    export default { 
    name: 'portfolio ',components: {

    } ,
    mounted(){
        // this.$store.dispatch('getProjects')
        console.log(this.myProject)
        this.myProjects=myProjects    
      },
    data () {
      return {
        myProjects:myProjects
            
      }
    },
    computed:{
        projectChunks(){
            return this.$store.getters.projectChunks
        },
        
    },
   methods:{
       icon_path(tech){
           console.log(tech)
            return require(`../assets/${tech.toLowerCase()}.png`)
       }
    }

}    
</script>

<style scoped>
.projects {
  margin: auto;
  padding: 5%;
  text-align: center;
  overflow: hidden;
}

.project {
  width: 50%;
  height: auto;
  margin: 2%;
  margin-left: auto;
  margin-right: auto;
  position: relative;
}

.project img {
  max-width: 100%;
  height: auto;
  display: block;
  margin: 0 auto;
  transition: transform 0.3s ease-in-out; 
}

.project .pa-3 {
  transition: transform 0.3s ease-in-out;
}

.project:hover .pa-3 {
  transform: scale(1.05);
}

.project:hover img {
  transform: scale(1.1);
}

.portfolio > h2{
  padding-left: 9%;
  text-transform: uppercase;
  font-weight: bold;
  color:var(--accent-color);
  padding-block:10;
  text-align: center;
  padding-block: 6%;
  font-size:2em;
}

.card-reveal {
  opacity: 0.85;
}

#description {
  font-size: 18px;
}

#project_name {
  font-size:28px;
}

.tech-icons {
  position: absolute;
  justify-content: space-around;
  padding: 1px;
  margin: 2px;
  bottom: 0px;
  width: 100%;
  left: 0;
  right: 0;
  margin: auto;
}

.portfolio > h2 {
  margin-right: 10rem;
}

@media (min-width: 768px) {
  .project {
    width: 50%;
  }
}

@media (min-width: 992px) {
  .project {
    width: 50%;
    min-width: 30rem;
  }
}

@media (max-width: 767px) {
  .project {
    width: 100%;
  }
}

.github-link {
  display: inline-block;
  text-decoration: none;
  font-size: 1.5rem;
  color: #950740;
  position: relative;
  /* overflow: hidden; */
  z-index: 1;
  /* padding-right: 10px; */
}

.github-link span {
  position: relative;
  display: inline-block;
  z-index: 1;
  /* padding-right: 20px; */
}

.github-link svg {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 0;
  width: 100%;
  height: 100%;
  fill: none;
}

.github-link path {
  stroke-dasharray: 300;
  stroke-dashoffset: 300;
  animation: dash 3s ease-in-out forwards infinite;
}

.github-link:hover path {
  stroke-dashoffset: 0;
}

@keyframes dash {
  to {
    stroke-dashoffset: 0;
  }
}


</style>