<template>
  <v-flex xs12 sm6 offset-sm3>
    <v-layout row justify-center>
      <!-- <v-btn color="primary" dark @click.stop="openDialog">Open Dialog</v-btn> -->

      <v-dialog v-model="dialog" max-width="290">
        <v-img src="https://cdn.vuetifyjs.com/images/cards/desert.jpg" aspect-ratio="2.75"></v-img>
        <v-card>
          <v-card-title class="headline">{{row.movie_title}}</v-card-title>
          <v-card-text>Let Google help apps determine location. This means sending anonymous location data to Google, even when no apps are running.</v-card-text>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-flex>
</template>

<script>
export default {
  props: ["row"],
  data() {
    return {
      dialog: false
    };
  },
  methods: {},
  watch: {
    row: function() {
      this.dialog = true;
    }
  }
};
</script>