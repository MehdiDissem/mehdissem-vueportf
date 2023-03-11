<template>
    <v-container fluid class="contact pa-2" id="contact">
      <v-container>
        <v-row class="py-8">
  
          <v-col class="info-text" xs="12" sm="12" md="6">
            <h2>
              Let's 
              <v-icon>
                mdi-arrow-right
              </v-icon>
            </h2>
            <h2>
              Connect
            </h2>
            <p>
              As a full stack JS developer with a background in marketing, I bring a unique perspective and set of skills to every project. With over 6 years of experience in various marketing fields, including digital marketing, SEO, and content creation, I understand how to build web applications that not only function flawlessly but also effectively reach and engage target audiences. From designing visually appealing user interfaces to developing robust backend solutions, I am passionate about creating applications that meet the needs of both users and businesses. If you're looking for a full stack JS developer with a marketing edge, let's connect and bring your project to the next level.
            </p>
          </v-col>
  
          <v-col class="form" xs="12" sm="12" md="6">
            <v-form ref="form">
              <v-text-field
                :rules="nameRules"
                v-model="name"
                class="text-field montserrat  my-8"
                placeholder="name"
                outlined
              ></v-text-field>
              <v-text-field
                :rules="emailRules"
                v-model="email"
                class="text-field montserrat my-8"
                placeholder="email"
                outlined
              ></v-text-field>
              <v-textarea
                :rules="messageRules"
                v-model="message"
                background-color="#CCCCCC"
                class="message-field montserrat my-8"
                placeholder="message"
                outlined
              ></v-textarea>
              <v-btn outlined medium @click="sendEmail" :loading="loading" class="montserrat  btn my-8" color="accent">
                {{ success ? 'Sent!' : 'Submit' }}
                </v-btn>
            </v-form>
          </v-col>
        </v-row>
      </v-container>
    </v-container>
  </template>

<script>
  import emailjs from 'emailjs-com';

  export default {
    name: 'contact',
    components: {},
    data() {
      return {
        loading: false,
        success:false,
        nameRules: [v => !!v || 'Name is required'],
        emailRules: [
          v => !!v || 'E-mail is required',
          v => /.+@.+/.test(v) || 'E-mail must be valid',
        ],
        messageRules: [v => !!v || 'Message is required'],
        name: '',
        email: '',
        message: ''
      }
    },
    methods: {
      sendEmail() {
        this.loading = true;
        emailjs.send("service_pno2xfd", "template_ct9a0mc", {
            from_name: this.name,
            from_email: this.email,
            message: this.message
          },"C6wIMZooGI-c6Wdeu")
          .then((response) => {
            console.log('SUCCESS!', response.status, response.text);
            this.loading = false;
            this.success = true;
            this.name = 'Name sent successfully';
            this.email = 'Email sent successfully';
            this.message='message sent successfully'
          }, (err) => {
            console.log('FAILED...', err);
            this.loading = false;
          });
      }
    }
  }
</script>

<style scoped lang="scss">

#contact{
    background-color:var( --main-bg-color);
}

.info-text{
  
    padding-right: 2%;
    h2{ 
        max-width:600px;
        width:100vw;  
        font-size: 3em;
        color:var(--highlight-color);
    }
    .mdi-arrow-right{
        font-size: 1.5em;
        color:var(--dark-accent);
    }

    p{
        color:var(--gray);
        font-weight: bold;
        font-size: 1.2em;
    }
}

    
.form{
   
    .text-field{
        height:55px;
        // padding:0;
         background-color: #d3d3d3;
        // background-color:var(--gray);
        
    }


.btn{
   font-weight: bold;
   border-width:3px ;
   color: var(--gray);
} 
}
.message-field{
    background-color: #fff;
}


/* .contact{
    margin:auto;
    margin-bottom: 20%;
    width:70%;
    max-width:35rem;
    background-color: #fff;
}

.contact>h2 {
    text-align: center;
    color: #a9a9a9;
    font-size: calc(1rem + 4vw );
}



.text-field{
    height:55px;
    padding:0;
    background-color: lightgrey;
}
*/

</style>
