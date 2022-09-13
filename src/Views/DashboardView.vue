<template>
    <div class="dashboard">
        <h1 class="subtitle-1 grey--text">Dashboard</h1>
        <v-container class="my-5 px-0 ">

            <v-layout row class="ma-0 mb-3">
                <v-tooltip top>
                <template v-slot:activator="{ on, attrs }">
                    <v-btn small plain color="grey" @click="sortBy('title')" v-bind="attrs" v-on="on">
                    <v-icon left small>mdi-folder</v-icon>
                    <span class="caption text-lowercase">By project name</span>
                    </v-btn>
                </template>
                <span>Sort projects by project name</span>
                </v-tooltip>
                <v-tooltip top>
                <template v-slot:activator="{on, attrs}">
                    <v-btn small plain color="grey" @click="sortBy('person')" v-bind="attrs" v-on="on">
                    <v-icon left small>mdi-account</v-icon>
                    <span class="caption text-lowercase">By person</span>
                    </v-btn>
                </template>
                <span>Sort projects by person name</span>
                </v-tooltip>
            </v-layout>

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
                        <div id="chips-container" class="text-right">
                            <v-chip small :class="`${project.status} white--text caption my-2`">{{project.status}}</v-chip>
                        </div>
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
    },
    methods: {
        sortBy(prop){
            this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
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
#chips-container .v-chip.complete{
    background:#3cd1c2;
}
#chips-container .v-chip.ongoing{
    background:orange;
}
#chips-container .v-chip.overdue{
    background:tomato;
}
</style>