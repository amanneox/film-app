<template>
  <v-app-bar
    fixed
    style="height: 120px;"
    class="pt-md-2 pt-4"
    color="white">
    <v-container
      style="display: inline-flex; justify-content: center;">
      <v-img
        contain height="40" max-width="40"
        :src="`https://image.flaticon.com/icons/svg/863/863133.svg`">
      </v-img>
      <v-img
        contain height="40" max-width="20" class="ml-5 mr-5"
        :src="`https://image.flaticon.com/icons/svg/1237/1237946.svg`">
      </v-img>
      <v-img
        contain height="40" max-width="40"
        :src="`https://image.flaticon.com/icons/svg/2700/2700657.svg`">
      </v-img>
    </v-container>
    <template v-slot:extension>
      <v-tabs align-with-title>
        <v-tab
          class="text-none"
          v-on:click="$emit('clicked', true)">
          Upcoming Movies
        </v-tab>
        <v-tab
          class="text-none"
          v-on:click="$emit('clicked', false)">
          Top Rated Movies
        </v-tab>
      </v-tabs>
    </template>
  </v-app-bar>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>
