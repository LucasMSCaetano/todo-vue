<template>
  <v-app class="grey light">
  <navbar />
    <v-content>
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
