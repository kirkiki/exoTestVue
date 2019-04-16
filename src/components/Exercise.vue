<template>
<v-stepper v-model="e1">
    <v-stepper-header>
      <v-stepper-step :complete="e1 > 1" step="1">Question 1</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step :complete="e1 > 2" step="2">Question 2</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="3">Question 3</v-stepper-step>
    </v-stepper-header>

    <v-stepper-items>
      <v-stepper-content step="1">
        <v-layout align-center justify-center column fill-height>
          <v-card class="mb-5" height="200px">
              <v-card-title primary-title>
                  <div>
                      <div class="headline">Select the right answer</div>
                      <span class="grey--text">It's nearly midday. _________ much work this morning?</span>
                  </div>
              </v-card-title>
              <div>
                <Mcbutton text="Reponse 1" isTrue="true" @change="changeQuestion"/>
                <Mcbutton text="Reponse 2"  @change="changeQuestion"/>
              </div>
          </v-card>
        </v-layout>

        <v-btn
          color="primary"
          @click="e1 = 2"
        >
          Next Question
        </v-btn>

        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>


<v-stepper-content step="2">
        <v-layout align-center justify-center column fill-height>
          <v-card class="mb-5" height="200px">
              <v-card-title primary-title>
                  <div>
                      <div class="headline">Select the right answer</div>
                      <span class="grey--text">It's nearly midday. _________ much work this morning?r</span>
                  </div>
              </v-card-title>
              <div>
                <Mcbutton text="Reponse 1" isTrue="true" @change="changeQuestion"/>
                <Mcbutton text="Reponse 2"  @change="changeQuestion"/>
              </div>
          </v-card>
        </v-layout>

        <v-btn
          color="primary"
          @click="e1 = 2"
        >
          Next Question
        </v-btn>

        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>
      <v-stepper-content step="3">
        <v-layout align-center justify-center column fill-height>
          <v-card class="mb-5" height="200px">
              <v-card-title primary-title>
                  <div>
                      <div class="headline">Select the right answer</div>
                      <span class="grey--text">It's nearly midday. _________ much work this morning?r</span>
                  </div>
              </v-card-title>
              <div>
                <Mcbutton text="Reponse 1" isTrue="true" @change="changeQuestion"/>
                <Mcbutton text="Reponse 2" @change="changeQuestion"/>
              </div>
          </v-card>
        </v-layout>

        <v-btn
          color="primary"
          @click="e1 = 2"
        >
          Next Question
        </v-btn>

        <v-btn flat>Cancel</v-btn>
      </v-stepper-content>



    </v-stepper-items>
  </v-stepper>
</template>

<script>
import Mcbutton from '@/components/Mc-button'
export default {
  components : {Mcbutton},
    data() {
        return {
            e1: 0,
            nbQuestion : 3
        }
    },
    methods: {
      changeQuestion : function(){
        // eslint-disable-next-line
        console.log(this.e1)
        let i = parseInt(this.e1)
        if(this.e1 == this.nbQuestion)
          this.e1 = 1
        else
          this.e1 = (i+1).toString()
      }
    },
}
</script>