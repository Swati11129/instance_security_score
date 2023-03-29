<template>
<div style="background-color:#d1dde8; width:100vw; height:100vh">
    <v-container class=" white my-5 " style="width: 60%;">
        <div class="text my-5 font-weight-bold text-h5 ">Instances Security Score</div>
            <div class="font-weight-bold d-flex  my-8" >
                <span style="width:35%" >
                    Instance Name
                </span>
                <div class=" mx-auto d-flex">
                    <img src="../assets/score icon.jpg" width="25" height="20" class="mr-2 my-auto">
                    <div>Score </div>
                </div>
                <span class=" mx-auto" style="width: 15%;">  
                    High Priority Issue
                </span>        
        </div>

        <div>
            <div color="primary">
                <div class="my-8 d-flex " v-for="(item, i) in items" :key="i">
                    <div class=" my-auto" style="width:35%">
                        <div v-text="item.text"></div>
                    </div>
                    <div  class="d-flex mx-auto  my-auto" style="">
                        <div  style="width:25px; height:13px" :style="{'background-color':score_color(item.score)}" class="rounded-pill my-auto mr-2  "/>
                        <div v-text="item.score"/>
                    </div>
                    <div class=" my-auto mx-auto d-flex justify-space-between" style="width:15%">
                            <v-progress-linear buffer-value="0"   class="rounded-pill  mr-2 my-auto" v-model="item.high_priority_issue" height="13"  />                        
                        <div v-text="item.high_priority_issue" />
                    </div>
                </div>
            </div>
        </div>
    </v-container>
</div>
</template>

<script>
export default {
    data: () => ({
        
        titles: [{
            text: 'Instance Name',
            score: 'Score',
            priority: 'High Priority Issue'
        }, ],
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

    }),
    methods:{
        score_color(score){
            if(score<=25){
                return '#6CB47F'
            }
            else if(score>25 && score<=50)
            {
                return '#F6B952'
            }
            else if(score>50 && score<=75)
            {
                return'#F69913'
            }
            else if(score>75 && score<=100)
            {
                return '#FF482C'
            }
        }
    }

   
}
</script>


