<template>
    <v-container id="tools">
        <v-row >

           <v-col class="" xs="12" sm="12"  md="4"> 
               <h2 id="title"> My tools </h2> 
            </v-col>
           
           <v-col class="tools-names " xs="12"  sm="12" md="4">
              <p> Languages</p>
              <p><img class="languages-icons" data-name="JavaScript" src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" alt="JavaScript" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png" @mouseenter="playTickSound" />
                
            
            </p>
            <p> Databases </p>
            <p>
                <img class="languages-icons" src="https://cdn.iconscout.com/icon/free/png-256/mongodb-5-1175140.png" @mouseenter="playTickSound" />
                <img class="languages-icons" src="https://cdn-icons-png.flaticon.com/512/5968/5968342.png" @mouseenter="playTickSound" />
                <img class="languages-icons" src="https://www.dcorba.com/wp-content/uploads/2017/11/mysql-logo.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://cdn.iconscout.com/icon/free/png-256/firebase-1-282796.png?f=webp&w=256" @mouseenter="playTickSound" />
            
            </p>

           </v-col>

           <v-col class="tools-names " xs="12"  sm="12" md="4" >
               <p>Front-end</p>
               <p>
                <img class="languages-icons" src="https://cdn1.iconfinder.com/data/icons/programing-development-8/24/react_logo-512.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://res.cloudinary.com/dlnvacfsc/image/upload/v1678271111/pngwing.com_3_vkfojc.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://cdn.cdnlogo.com/logos/n/80/next-js.svg" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRRRS42xTcnXMlC85s502uVAhzdGqq_23-bXA&usqp=CAU" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/512px-HTML5_logo_and_wordmark.svg.png?20170517184425" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://cdn.freebiesupply.com/logos/large/2x/css3-logo-png-transparent.png" @mouseenter="playTickSound"/>
            
            
                </p>
              <p> Back-end</p>
              <p>
                <img class="languages-icons" src="https://seeklogo.com/images/N/nodejs-logo-FBE122E377-seeklogo.com.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://bs-uploads.toptal.io/blackfish-uploads/components/skill_page/content/logo_file/logo/195562/express_js-161052138fa79136c0474521906b55e2.png" @mouseenter="playTickSound"/>
                <img class="languages-icons" src="https://d2eip9sf3oo6c2.cloudfront.net/tags/images/000/001/287/square_480/prismaHD.png" @mouseenter="playTickSound"/>
            
                </p>
           </v-col>

        </v-row>
    </v-container>
</template>


<script>
import { Howl } from 'howler';
import tickSoundFile from '@/assets/tick.mp3';
export default {
    name:"tools",
    data() {
    return {
      tickSound: new Howl({ src: tickSoundFile }),
        };
    },
    methods: {
    playTickSound() {
      this.tickSound.play();
    },
  },
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