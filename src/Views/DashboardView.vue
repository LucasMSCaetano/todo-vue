<template>
    <div class="dashboard">
        <h1 class="subheading grey--text">Dashboard</h1>
        <v-container class="my-5">
            <v-card flat v-for="project in projects" :key="project.title">
                <v-layout row wrap :class="`pa-3 project ${project.status}`">
                    <v-flex xs12 md6>
                        <div class="caption grey--text" >Project title</div>
                        <div>{{project.title}}</div>
                    </v-flex>
                    <v-flex xs6 sm4 md2>
                        <div class="caption grey--text" >Person</div>
                        <div>{{project.person}}</div>
                    </v-flex>
                    <v-flex xs6 sm4 md2>
                        <div class="caption grey--text" >Due by</div>
                        <div>{{project.due}}</div>
                    </v-flex>
                    <v-flex xs6 sm4 md2>
                        <div class="caption grey--text" >Status</div>
                        <div>{{project.status}}</div>
                    </v-flex>
                </v-layout>
                <v-divider-inset-margin-top/>
            </v-card>
        </v-container>
    </div>
</template>

<script>
export default {
    data(){
        return{
            projects:[
                {title: 'design a new site', person:'the Net Ninja', due: '1st jan', status:'ongoing', content: 'aaaa'},
                {title: 'code', person:'Chun Li', due: '1st jan', status:'complete', content: 'aaaa'},
                {title: 'design videp', person:'Ryu', due: '1st jan', status:'complete', content: 'aaaa'},
                {title: 'create a community', person:'Gouken', due: '1st jan', status:'overdue', content: 'aaaa'},
            ]
        }
    }
}
</script>

<style>
.project.complete{
    border-left: 4px solid #3cd1c2;
}
.project.ongoing{
    border-left: 4px solid orange;
}
.project.overdue{
    border-left: 4px solid tomato;
}
</style>