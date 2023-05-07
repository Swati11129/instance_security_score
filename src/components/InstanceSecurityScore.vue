<!-- <template>
<div style="background-color:#d1dde8; width:100vw; height:100vh">
    <v-container class=" white mt-5 pa-10  " style="width: 50%;">
        <div class="font-weight-bold text-h5 mb-6 ml-4">Instances Security Score</div>
        <v-simple-table style=" pointer-events: none; " >
            <thead  style="border: hidden !important;" >
                <tr >
                    <th>
                        Instance Name
                    </th>
                    <th >
                        <div class="d-flex " style="gap:5px">
                            <img src="../assets/score icon.jpg" width="25" height="20" class="my-auto">
                            <div>Score </div>
                        </div>
                    </th>
                    <th >
                        High Priority Issue
                    </th>
                </tr>
            </thead>
            
            <tbody >
                <tr  v-for="item in items" :key="item.name">
                    <td>{{ item.text }}</td>
                    <td>
                        <div class="d-flex" style="gap:10px">
                            <div style="width:25px; height:13px" :style="{'background-color':score_color(item.score)}" class="rounded-pill my-auto" />
                            <div v-text="item.score" />
                        </div>
                    </td>
                    <td  >   
                            <div class="d-flex" style="gap:10px; ">
                                <div class="my-auto" :style="{'width':item.high_priority_issue+'%' } ">
                                    <v-progress-linear color="#83A3FE" class="rounded-pill " value="100" height="13" />
                                </div>
                                <div>{{item.high_priority_issue}}</div>
                            </div>
                    </td>
                </tr>
            </tbody>
        </v-simple-table>
    </v-container>
</div>
</template>

<script>
export default {
    data() {
        return {
            items: [{
                    text: 'Instance_Dev',
                    score: 91,
                    high_priority_issue: 100
                },
                {
                    text: 'Instance_Prod',
                    score: 76,
                    high_priority_issue: 80
                },
                {
                    text: 'Instance_Test',
                    score: 54,
                    high_priority_issue: 50
                },
                {
                    text: 'Instance_QA',
                    score: 43,
                    high_priority_issue: 30
                },
                {
                    text: 'Instance_Finance',
                    score: 23,
                    high_priority_issue: 20
                },
            ],
        }
    },
    methods: {
        score_color(score) {
            if (score <= 33) {
                return 'green'
            } else if (score > 33 && score <= 75) {
                return 'orange'
            } else if (score > 75 && score <= 100) {
                return 'red'
            }
        }
    }

}
</script>

<style>
tbody td, th {
    border: hidden !important;
}
tr th{
   font-weight: bold !important;
   font-size: 14px !important;
    color: black !important;
}

tr{
  height: 60px !important;
}
</style>  -->

<template>
  <div style="background-color: #d1dde8; width: 100vw; height: 100vh">
    <v-container  class="white pa-10 " style="width: 45%">
      <div class="font-weight-bold text-h5 mb-8">Instances Security Score</div>
      <v-row>
        <v-col class="font-weight-medium" >Instance Name</v-col>
        <v-col>
          <div class="d-flex" style="gap: 5px">
            <img
              src="../assets/score icon.jpg"
              width="25"
              height="20"
    
            />
            <div class="font-weight-medium">Score</div>
          </div>
        </v-col>
        <v-col class="font-weight-medium">High Priority Issue</v-col>
      </v-row>

      <v-row v-for="(item, i) in items" :key="i" class="mb-3">
        <v-col >{{ item.text }}</v-col>
        <v-col>
          <div class="d-flex" style="gap: 10px">
            <div
              style="width: 25px; height: 13px"
              :style="{ 'background-color': score_color(item.score) }"
              class="rounded-pill my-auto"
            />
            <!-- <div v-text="item.score" /> -->
            <div>{{ item.score }}</div>
          </div>
        </v-col>
        <v-col>
          <div class="d-flex" style="gap: 10px">
            <div
              class="d-flex"
              :style="{ 'width': item.high_priority_issue + '%' }"
            >
              <v-progress-linear
                color="#83A3FE"
                class="rounded-pill my-auto"
                value="100"
                height="13"
              />
            </div>
            <div>{{ item.high_priority_issue }}</div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data(){
    return{
    items: [
      {
        text: "Instance_Dev",
        score: 91,
        high_priority_issue: 100,
      },
      {
        text: "Instance_Prod",
        score: 76,
        high_priority_issue: 80,
      },
      {
        text: "Instance_Test",
        score: 54,
        high_priority_issue: 50,
      },
      {
        text: "Instance_QA",
        score: 43,
        high_priority_issue: 30,
      },
      {
        text: "Instance_Finance",
        score: 23,
        high_priority_issue: 20,
      },
    ],
  }
},
  methods: {
    score_color(score) {
      if (score <= 33) {
        return "green";
      } else if (score > 33 && score <= 75) {
        return "orange";
      } else if (score > 75 && score <= 100) {
        return "red";
      }
    },
  },
};
</script>
