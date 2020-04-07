<template>
  <v-app>
    <Navbar @clicked="switchTab"/>
    <UpcomingMovies style="margin-top: 100px;" v-if="change"/>
    <TopRatedMovies style="margin-top: 100px;" v-else/>
  </v-app>
</template>

<script>
import Navbar from './components/Navbar';
import UpcomingMovies from './pages/UpcomingMovies';
import TopRatedMovies from './pages/TopRatedMovies';

export default {
  name: 'App',

  components: {
    Navbar,
    UpcomingMovies,
    TopRatedMovies
  },

  data: () => ({
    change: true
  }),

  methods: {
    switchTab(value) {
      if(value == false) {
        this.change = false
      }
      else { this.change = true }
    }
  }
};
</script>
