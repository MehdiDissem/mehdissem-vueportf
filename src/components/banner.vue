<template>
    <div class="banner d-flex flex-column justify-center align-items-center" @mousemove="moveCircle">
        <div class="circle" :style="{ left: circlePos.x + 'px', top: circlePos.y + 'px' }"></div>
        <div class="intro">
            <p class="ma-0 pa-0" v-on:mouseover="changeMessage">{{ message }}</p>
            <h1 class="heading ma-0 pa-0">
                My name is
                <span class="animated-text">M</span>
                <span class="animated-text">e</span>
                <span class="animated-text">h</span>
                <span class="animated-text">d</span>
                <span class="animated-text">i</span>
                <span class="animated-text">&nbsp;</span>
                <span class="animated-text">D</span>
                <span class="animated-text">i</span>
                <span class="animated-text">s</span>
                <span class="animated-text">s</span>
                <span class="animated-text">e</span>
                <span class="animated-text">m</span>
            </h1>
            <h2 class="secondary-text"  v-on:mouseover="changeQuote" v-html="quoteWithSpan"></h2>
            <v-btn color="accent" outlined class="btn my-8" @click="showResumeDialog = true">View Resume</v-btn>
            <v-dialog v-model="showResumeDialog" width="80%">
              <object :data="resume" type="application/pdf" width="100%" height="600px">
                <embed :src="resume" type="application/pdf" width="100%" height="600px" />
                <p>Your web browser doesn't have a PDF plugin. Instead, you can <a :href="resume">click here to download the PDF file.</a></p>
              </object>
            </v-dialog>
        </div>
        
    </div>
  </template>
  
  <script>
  import resume from '@/assets/Resume-Mehdi-Dissem.pdf'
  export default {
    name: "banner",
    data() {
      return {
        messages: ["Hello !", "Bonjour !", "Hola !", "こんにちは！"],
        message: "Hello !",
        quotes: [
          `I'm not a great programmer, I'm just a good programmer with <span class='highlight'>great habits</span>.`,
          "I <span class='highlight'>solve</span> the problem first. Then I write the code.",
          "I make it <span class='highlight'>work</span>, I make it <span class='highlight'>right</span> then I make it <span class='highlight'>fast</span>.",
          "Simplicity is the soul of my <span class='highlight'>efficiency</span>.",
          "I fix the <span class='highlight'>cause</span>, not the symptom."
        ],
        quoteIndex: 0,
        circlePos: { x: 0, y: 0 },
        showResumeDialog: false,
        resume: ""
      };
    },
    mounted() {
    // set the resume data property to the imported pdf file
    this.resume = resume;
  },
    computed: {
      quoteWithSpan() {
        return this.quotes[this.quoteIndex];
      }
    },
    methods: {
      changeMessage() {
        const randomIndex = Math.floor(Math.random() * this.messages.length);
        this.message = this.messages[randomIndex];
      },
      changeQuote() {
        this.quoteIndex = Math.floor(Math.random() * this.quotes.length);
      },
      moveCircle(event) {
        this.circlePos = { x: event.clientX, y: event.clientY };
    },
    toggleOverlay() {
      this.showResumeDialog = !this.showResumeDialog;
    }
  }
  }
  </script>
  
  <style lang="scss">

// .highlight {
//     color: var(--highlight-color);
//   }
    .banner {
        text-align: left;
        height: 100vh;
        width: 100vw;
        background-color: var(--main-bg-color);
        padding: 10%;
        position:relative
    }
    .circle {
        position: absolute;
        width: 100px;
        height: 100px;
        border-radius: 50%;
        background-color: yellow;
        pointer-events: none; 
    }
    @media screen and (max-width: 768px) {
      .circle {
        display: none;
      }
    }

    .secondary-text:hover::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(255, 255, 255, 0.5);
    z-index: -1;
    }

  .intro {
    p {
      margin-left: 10px;
      padding: 0;
      font-size: 1.5em;
      font-weight: bold;
      color: var(--dark-accent);
    }

    span {
      color: var(--dark-accent);
    }

    .btn {
      color: var(--gray);
    }

    .secondary-text {
      color: var(--gray);
      position: relative;
    }

    .heading {
      margin: 0px;
      padding: 0px;
      font-size: 4em;
      color: var(--highlight-color);
    }

    .animated-text {
      display: inline-block;
      animation: fade 2s ease-in-out infinite;
      opacity: 0;
    }

    .animated-text:nth-child(2n) {
      animation-delay: 0.5s;
    }

    }
    .animated-text:hover {
    animation-play-state: paused;
    opacity: 1;
    transform: translateX(0);
    }
  
  

  @keyframes glitch {
    0% {
      transform: translate(0, 0);
    }
    25% {
      transform: translate(2px, -2px);
    }
    50% {
      transform: translate(-2px, 2px);
    }
    75% {
      transform: translate(-2px, -2px);
    }
    100% {
      transform: translate(2px, 2px);
    }
  }

  @keyframes fade {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }
</style>