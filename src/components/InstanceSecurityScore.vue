<template>
<div style="background-color:#d1dde8; width:100vw; height:100vh">
    <v-container class=" white my-5 cyan">
        <div class="text my-4 font-weight-bold text-h5 white  ">Instances Security Score</div>
        <div>
            <div class="font-weight-bold d-flex white  " v-for="(title, i) in titles" :key="i">
                <span style="width:35%" class="blue">
                    <div v-text="title.text"></div>
                </span>
                <span style="width: 25%;" class="red">
                    <div v-text="title.score"> </div>
                </span>
                <span class="purple">
                    <div v-text="title.priority"></div>
                </span>
            </div>
        </div>

        <div>
            <div color="primary">
                <div class="my-5 d-flex indigo" v-for="(item, i) in items" :key="i">
                    <div class="blue my-auto" style="width:35%">
                        <div v-text="item.text"></div>
                    </div>
                    <div  class="d-flex red my-auto" style="width:25%">
                        <div  style="width:25px; height:13px" :style="{'background-color':bg_color}" class="rounded-pill my-auto   "/>
                        <div v-text="item.score"/>
                    </div>
                    <div class="purple my-auto" style="width:20%">
                        <div>
                            <v-progress-linear   class="rounded-pill " v-model="item.high_priority_issue" height="13"  />
                        </div>
                        <div v-text="item.high_priority_issue"></div>
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
        // isLoading: true,
        bg_color:'yellow',
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

   
}
</script>


