<template>
  <div class="projects">
    <h1 class="subtitle-1 grey--text">Projects</h1>

    <v-container class="my-5">
      <v-expansion-panels>
        <v-expansion-panel class="px-4" v-for="project in myProjects" :key="project.title">
          <v-expansion-panel-header>
            {{ project.title }}
          </v-expansion-panel-header>
          <v-expansion-panel-content class="grey--text">
            <div class="font-weight-bold">due by {{ project.due }}</div>
            <div>{{ project.content }}</div>
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>

  </div>
</template>

<script>

export default {
  name: 'ProjectsView',
  data() {
    return {
      projects: [
        {title: 'design a new site', person:'The Net Ninja', due: '1st jan', status:'ongoing', content: 'aaaa'},
                {title: 'code', person:'Chun Li', due: '1st jan', status:'complete', content: 'aaaa'},
                {title: 'design videp', person:'Ryu', due: '1st jan', status:'complete', content: 'aaaa'},
                {title: 'create a community', person:'Gouken', due: '1st jan', status:'overdue', content: 'aaaa'}
      ]
    }
  },
  computed: {
    myProjects() {
      return this.projects.filter(project => {
        return project.person === 'The Net Ninja'
      })
    }
  }
}
</script>