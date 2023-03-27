<template>
<div style="background-color:#d1dde8; width:100vw; height:100vh">
    <v-container class=" white my-5">
        <v-container class="text my-4 font-weight-bold text-h5 white  ">Instance Security Score</v-container>

        <v-list>
            <v-list-item-group color="primary">
                <v-list-item class="font-weight-bold" v-for="(title, i) in titles" :key="i">
                    <v-list-item-content>
                        <v-list-item-title v-text="title.text"></v-list-item-title>
                    </v-list-item-content>
                    <v-list-item-content>
                        <v-list-item-title v-text="title.score"> </v-list-item-title>

                    </v-list-item-content>
                    <v-list-item-content>

                        <v-list-item-title v-text="title.priority"></v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>

        <v-list>
            <v-list-item-group color="primary">
                <v-list-item class="my-5" v-for="(item, i) in items" :key="i">
                    
                    <v-list-item-content>
                        <v-list-item-title v-text="item.text"></v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-content class="mx-5">
                        <span style="width:2px; background-color:purple; height:3px"></span>
                        <v-list-item-title v-text="item.score"></v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-content>
                        <v-progress-linear v-show="isLoading" class="rounded-pill" v-model="item.high_priority_issue" height="10" />
                        <v-list-item-title v-text="item.high_priority_issue"></v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list-item-group>
        </v-list>

    </v-container>
</div>
</template>

<script>
export default {
    data: () => ({
        isLoading: true,
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

    watch() {
        data: {
            this.isLoading = false
        }
    },
}
</script>

<style>
.box {
    background-color: aqua;

}

.text {
    background: #d24b4b;
}
</style>
