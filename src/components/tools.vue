<template>
    <v-container id="tools">
        <v-row >

           <v-col class="" xs="12" sm="12"  md="4"> 
               <h2 id="title"> My tools </h2> 
               <div class="sound-div" @click="snackbar=true">
                   <p>(Click me then hover over the icons</p>
                   <p>for a nice sound)</p>
               </div>
            </v-col>
           
           <v-col class="tools-names " xs="12"  sm="12" md="4">
              <p> Languages</p>
              <p>
                <v-tooltip text="JavaScript" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" data-name="JavaScript" src="https://upload.wikimedia.org/wikipedia/commons/6/6a/JavaScript-logo.png" alt="JavaScript" @mouseenter="playTickSound"  target="_blank"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="TypeScript" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="Python" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png" @mouseenter="playTickSound" />
                  </template>
                </v-tooltip>
                
            
            </p>
            <p> Databases </p>
            <p>
              <v-tooltip text="MongoDB" location="top">
                <template v-slot:activator="{ props }">
                  <img class="languages-icons" v-bind="props" src="https://cdn.iconscout.com/icon/free/png-256/mongodb-5-1175140.png" @mouseenter="playTickSound" />
                </template>
              </v-tooltip>

              <v-tooltip text="PostgreSQL" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://cdn-icons-png.flaticon.com/512/5968/5968342.png" @mouseenter="playTickSound" />
                  </template>
                </v-tooltip>

                <v-tooltip text="MySQL" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://www.dcorba.com/wp-content/uploads/2017/11/mysql-logo.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>
                <v-tooltip text="FireBase" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://cdn.iconscout.com/icon/free/png-256/firebase-1-282796.png?f=webp&w=256" @mouseenter="playTickSound" />
                  </template>
                </v-tooltip>
            
            </p>

           </v-col>

           <v-col class="tools-names " xs="12"  sm="12" md="4" >
               <p>Front-end</p>
               <p>
                <v-tooltip text="React" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://cdn1.iconfinder.com/data/icons/programing-development-8/24/react_logo-512.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>
                <v-tooltip text="ReactNative" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props"  src="https://res.cloudinary.com/dlnvacfsc/image/upload/v1680291873/samples/pngwing.com_7_nfeg4f.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="Vue" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="NextJS" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://cdn.cdnlogo.com/logos/n/80/next-js.svg" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="Expo" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRRRS42xTcnXMlC85s502uVAhzdGqq_23-bXA&usqp=CAU" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="HTML" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/512px-HTML5_logo_and_wordmark.svg.png?20170517184425" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="CSS" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://cdn.freebiesupply.com/logos/large/2x/css3-logo-png-transparent.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>
            
            
                </p>
              <p> Back-end</p>
              <p>

                <v-tooltip text="NodeJS" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://res.cloudinary.com/dlnvacfsc/image/upload/v1680284101/samples/pngwing.com_5_rjnbjf.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="Express" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://res.cloudinary.com/dlnvacfsc/image/upload/v1680294186/pngwing.com_9_l9ry0z.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="Prisma" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://d2eip9sf3oo6c2.cloudfront.net/tags/images/000/001/287/square_480/prismaHD.png" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>

                <v-tooltip text="SocketIO" location="top">
                  <template v-slot:activator="{ props }">
                    <img class="languages-icons" v-bind="props" src="https://socket.io/images/logo.svg" @mouseenter="playTickSound"/>
                  </template>
                </v-tooltip>
                </p>
           </v-col>

        </v-row>
    </v-container>
              <v-snackbar
                v-model="snackbar">
                yay :D
                <template v-slot:actions>
                  <v-btn
                    color=var(--accent-color)
                    variant="text"
                    @click="snackbar = false"
                  >
                    Close
                  </v-btn>
                </template>
              </v-snackbar>
</template>


<script>
import { Howl } from 'howler';
import tickSoundFile from '@/assets/tick.mp3';
export default {
    name:"tools",
    data() {
    return {
      tickSound: new Howl({ src: tickSoundFile }),
      snackbar:false
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

   @media (max-width: 600px) {
    .sound-div {
      display: none;
    }
  }

  .sound-div {
  animation: bounce 1s infinite;
  font-weight: bold;
  margin-top: 15px;
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}
</style>