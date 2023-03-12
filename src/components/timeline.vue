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
    margin-left: -7%;
    margin-bottom: 20px;
  }
  
  .backgr{
    background-color: var(--main-bg-color);
    padding: 5%;
  }
  
  .timeline {
    margin: 30px 0;
  }
  
  .timeline-item {
    position: relative;
    padding: 20px 0;
  }
  
  .timeline-item::before {
    content: '';
    position: absolute;
    left: -12px;
    top: 50%;
    transform: translateY(-50%);
    height: 12px;
    width: 12px;
    border-radius: 50%;
    background-color: white;
  }
  
  .timeline-content {
    font-size: 16px;
    margin-left: 32px;
    color: white;
  }
  
  .timeline-position {
    margin-top: 0;
    margin-bottom: 10px;
    font-size: 18px;
  }
  
  .timeline-responsibilities {
    margin-top: 0;
    margin-bottom: 0;
    padding-left: 20px;
    list-style-type: disc;
    font-size: 14px;
  }
  
  .timeline-company {
    color: var(--accent-color);
    font-weight: bold;
    text-align: center;
    margin-top: 10px;
    margin-bottom: 20px;
    font-size: 16px;
  }
  
  @media screen and (max-width: 768px)  {
    #title{
      font-size: 20px;
      margin-left: 0;
    }
  
    .backgr{
      padding: 2%;
    }
  
    .timeline-content{
      font-size: 14px;
      margin-bottom: 10px;
    }
  
    .timeline {
      margin: 20px 0;
    }
  
    .timeline-position {
      font-size: 16px;
    }
  
    .timeline-company {
      font-size: 14px;
      margin-top: 5px;
      margin-bottom: 10px;
    }
  
    .timeline-responsibilities {
      margin-top: 5px;
      margin-bottom: 10px;
      font-size: 14px;
    }
  
    .timeline-item::before {
      display: none;
    }
  }
</style>
