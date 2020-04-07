<template>
  <v-layout>
    <v-flex>
      <v-container grid-list-sm fluid>
        <v-layout row wrap>
          <v-flex
            v-for="movie in movie_result"
            :key="movie.id"
            sm6 xs12 md3
            d-flex>
            <CardView
              :mv_poster="movie.poster_path"
              :mv_votes="movie.vote_average"
              :mv_vtcount="movie.vote_count"
              :mv_title="movie.title"
              :mv_desc="movie.overview.slice(0, 110).concat('...')"
              :mv_release="movie.release_date"/>
          </v-flex>
        </v-layout>
      </v-container>
      <v-overlay
        v-if="fetched"
        :opacity="0">
        <v-progress-circular
          :size="40"
          :width="5"
          color="primary"
          indeterminate>
        </v-progress-circular>
      </v-overlay>
    </v-flex>
  </v-layout>
</template>

<script>
  import axios from 'axios';
  import CardView from '../components/CardView';

  export default {
    data: () => ({
      movie_result: [],
      fetched: true
    }),
    components: {
      CardView
    },
    methods: {
      getTopRatedMovies() {
        axios.get('https://api.themoviedb.org/3/movie/top_rated?api_key=1b02a7fe41d6cac156bee8fbe176c277&language=en-US&page=1')
         .then(response => {
           this.movie_result = response.data.results;
           this.fetched = false
         })
         .catch(err => {
           console.log('Issue', err);
         });
      }
    },
    beforeMount: function() {
      this.getTopRatedMovies();
    }
  }
</script>
