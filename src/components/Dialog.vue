<template>
  <v-flex>
    <v-layout row justify-center>
      <!-- <v-btn color="primary" dark @click.stop="openDialog">Open Dialog</v-btn> -->
      <v-dialog v-model="dialog" max-width="600">
        <v-img src="https://cdn.vuetifyjs.com/images/cards/desert.jpg" aspect-ratio="2.75"></v-img>

        <v-card id="card">
          <v-card-title class="headline">
            {{ row.movie_title }}
            <v-card-actions> 
              <v-btn round color="primary" dark v-on:click="addRow">Add</v-btn>
            </v-card-actions>
          </v-card-title>

          <v-card-text v-for="(value, index) in row" :key="`value-${index}`">
            <span id="index">{{ index }}</span> :
            <span id="value">{{ value }}</span>
          </v-card-text>
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
    }
  }
};
</script>

<style scoped>
#card {
  text-align: left;
}
#index {
  color: #42b983;
  font-weight: bold;
}
</style>