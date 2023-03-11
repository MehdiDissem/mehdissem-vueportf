<template>
    <div class="backgr">
        <h2 id="title"> My process </h2> 
        <v-timeline class="timeline desktop-only" direction="horizontal" line-inset="12">
          <v-timeline-item v-for="experience in myExperiences" :key="experience.position" class="timeline-item">
            <template v-slot:opposite>
              <div class="timeline-company">
                {{ experience.company }}
                <br>
                {{ experience.start_date }} - {{ experience.end_date ? experience.end_date : 'Present' }}
              </div>
            </template>
            <div class="timeline-content">
              <h3 class="timeline-position">{{ experience.position }}</h3>
              <ul class="timeline-responsibilities">
                <li v-for="responsibility in experience.responsibilities" :key="responsibility">{{ responsibility }}</li>
              </ul>
            </div>
          </v-timeline-item>
        </v-timeline>
    </div>
  </template>
  
  <script>
  import myExperiences from '@/store/workExperiences';
  
  export default {
    name: 'timeline',
    data() {
      return {
        myExperiences: myExperiences.sort((a, b) => new Date(a.start_date) - new Date(b.start_date))
      }
    }
  }
  </script>
  
  <style scoped>
  #title{
    width: 100vw;
    text-transform: uppercase;
    font-weight: bold;
    color: var(--accent-color);
    padding-top: 15px;
    text-align: center;
    margin-left:-7%
}
    .backgr{
    background-color: var(--main-bg-color);
    height: 100vh;
    width: 100vw;
    padding: 5%;
    
    }
  
  .timeline {
    margin: 50px 0px;
    
  }
  
  .timeline-item {
    position: relative;
    padding: 20px 0;
    
  }
  
  .timeline-item::before {
  content: '';
  position: absolute;
  left: -12px;
  top: 51.8%;
  transform: translateY(-50%);
  height: 12px;
  width: 12px;
  border-radius: 50%;
  background-color: white;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.5);
  }
  70% {
    box-shadow: 0 0 0 10px rgba(255, 255, 255, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(255, 255, 255, 0);
  }
}
  
  
  
  .timeline-content {
    font-size: 15px;
    margin-left: 32px;
    color:white;
  }
  
  .timeline-position {
    margin-top: 0;
    margin-bottom: 10px;
  }
  
  .timeline-responsibilities {
    margin-top: 0;
    margin-bottom: 0;
    padding-left: 20px;
    list-style-type: disc;
  }
  
  .timeline-company {
    color: var(--accent-color);
    font-weight: bold;
    text-align: right;
  }

  @media screen and (max-width: 768px)  {

    #title{
    width: 100vw;
    text-transform: uppercase;
    font-weight: bold;
    color: var(--accent-color);
    padding-top: 15px;
    text-align: center;
    margin-bottom:20px;
}
    .backgr{
    background-color: var(--main-bg-color);
    height: auto;
    width: auto;
      }
  .timeline-content{
    font-size: 5px;
    margin-bottom:20px;
  }
  .timeline {
    direction: vertical;
  }
  .desktop-only {
    display:contents;
  }
  
  
  .timeline-position {
    font-size: 17px;
    margin-bottom:20px;
  }
  
  .timeline-company {
    margin-top: 10px;
    margin-bottom:20px;
    font-size: 14px;
    font-weight: bold;
    text-align: center;
  }
  
  .timeline-responsibilities {
    margin-top: 5px;
    margin-bottom: 20px;
    list-style-type:disc;
    font-size: large;
  }
  .timeline-item::before {
    animation: none;
  }
}

  </style>