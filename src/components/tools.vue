<template>
    <v-container id="tools">
        <v-row >

           <v-col class="" xs="12" sm="12"  md="4"> 
               <h2 id="title"> My tools </h2> 
            </v-col>
           
           <v-col class="tools-names " xs="12"  sm="12" md="4">
              <p> Languages</p>
              <p><img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" />
                <img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png" />
            
            </p>

           </v-col>

           <v-col class="tools-names " xs="12"  sm="12" md="4" >
               <p>Front-end</p>
              <p> Back-end</p>
              <p> Databases </p>
           </v-col>

        </v-row>
    </v-container>
</template>


<script>
export default {
    name:"tools",
}
</script>

<style lang="scss" scoped >
    $small: 300px;
    $medium: 900px;

   #tools {
       padding: auto;
       margin: auto;
       height:auto;
       background-color : white;

       #title{
        //    width:100vw;
           text-transform: uppercase;
           font-weight: bold;
           color:var(--accent-color);
           padding-top:15px;

       }
       
     
       @media  screen and (min-width:$small) {
          padding:10%;

          #title {
              width: 100vw;
          }
           
        //    background-color:red;
       }

       @media  screen and (min-width:$medium) {
           padding-block: 10%;
           padding-left:15%;
        //    background-color:red;
       }

       .tools-names {
        margin-inline: 0px;

        p {
            font-family: var(--secondary-font);
            font-size: 2em;
            color: var(--main-bg-color);
            transition: font-size 0.3s ease-in-out;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 10px;
            cursor: pointer;
        }

        p:hover {
            color: var(--gray);
            font-size: 2.2em;
            font-weight: medium;
        }

        .languages-icons {
            width: 40px;
            height: 40px;
            margin-right: 10px;
            transition: transform 0.2s;
        }

        .languages-icons:hover {
            transform: scale(1.1);
        }
        }
   }
</style>