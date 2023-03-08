<template>
    <v-container fluid class="ma-0 portfolio" id="portfolio">
      <h2 class="">Portfolio</h2>
      <v-container fluid class="projects pa-0 pa-md-4">
        <v-row align="center" justify="center" class="mx-0">
          <v-col cols="12" md="5" v-for="(project, index) in myProjects" :key="index">
            <v-hover v-slot="{ hover }">
              <v-card class="mb-4 grey project" elevation="2" round>
                <v-img
                  :src="project.picture"
                  width="100%"
                  max-height="340px"
                  class="d-flex align-center justify-center"
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
    },
    data () {
      return {
        myProjects
            
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
</style>