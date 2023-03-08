<template>
    <div id="about"> 
      <v-row>
          <v-col class="col-xs-12">            
            <h2> ABOUT ME</h2>
            <p>
            <p> 
                As a Full Stack web developer, I possess a strong commitment to excellence, a collaborative mindset, and effective communication skills. 
            </p> 
            <p>
                Drawing upon six years of experience across diverse marketing fields, including article writing, SEO, freelancing, and market analysis, I have honed a versatile set of technical and non-technical skills. 
                </p>
            <p>
                I am now seeking new opportunities in the IT field to further enhance my technical abilities and contribute to innovative projects.

            </p>
        </p>
          </v-col>
          <v-col class="col-xs-12">
              <v-img src="../assets/mehdidissem.png" max-width="500px" contain >

              </v-img>
          </v-col>
      </v-row>
    </div>
</template>

<script>
export default {
    name : 'about'
}
</script>


<style lang="scss" scoped > 
    #about{
        padding-left: 10%;

       h2{  
           text-transform: uppercase;
           font-weight: bold;
           color:var(--accent-color);
           padding-top:15px;
        }
        p {
             padding-block: 10px;
             padding-right: 10px;
             font-weight: 400;
             color: var(--gray);
             font-size: 1.3em;
        }
    }

</style>