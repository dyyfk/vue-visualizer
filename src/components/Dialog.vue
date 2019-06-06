<template>
  <v-flex>
    <v-layout row justify-center>
      <!-- <v-btn color="primary" dark @click.stop="openDialog">Open Dialog</v-btn> -->

      <v-dialog v-model="dialog" max-width="290">
        <v-img src="https://cdn.vuetifyjs.com/images/cards/desert.jpg" aspect-ratio="2.75"></v-img>
        <v-card>
          <v-card-title class="headline">{{row.movie_title}}</v-card-title>
          <v-card-text>{{row.director_name}}</v-card-text>
          <v-card-actions>
            <v-btn flat color="orange" v-on:click="addRow">Add</v-btn>
          </v-card-actions>
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
  methods: {
    addRow() {
      this.$emit("add-row", this.row);
    }
  },
  watch: {
    row() {
      this.dialog = true;
    },

  }
};
</script>