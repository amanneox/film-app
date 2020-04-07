<template>
    <v-card
    :loading="loading"
    class="mx-auto my-12"
    max-width="300">
    <v-img
      contain
      :src="`http://image.tmdb.org/t/p/w500${mv_poster}`">
    </v-img>
    <v-card-title class="mv_title">{{mv_title}}</v-card-title>
    <v-card-text>
      <v-row
        align="center"
        class="mx-0">
        <div class="black--text">{{mv_votes}}/10&nbsp;({{mv_vtcount}})</div>
        <v-spacer></v-spacer>
        <div class="black--text">{{mv_release}}</div>
      </v-row>
      <v-divider class="mt-4 mb-4"></v-divider>
      <div class="mv_desc">{{mv_desc}}</div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: [
    'mv_poster',
    'mv_title',
    'mv_votes',
    'mv_vtcount',
    'mv_desc',
    'mv_release'
  ],
  data: () => ({
  }),
  methods: {
    reserve() {
      this.loading = true
      setTimeout(() => (this.loading = false), 2000)
    }
  }
}
</script>
