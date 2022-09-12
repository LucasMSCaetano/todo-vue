<template>
  <v-app class="grey light">
  <navbar />
    <v-content class="mx-4 mb-4">
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
import Navbar from '@/components/NavBar.vue'

export default {
  name: 'App',
  components: {Navbar},
  data: () => ({
    //
  }),
};
</script>
