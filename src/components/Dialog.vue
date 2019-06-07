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
            <span id="value" v-if = "!strip(value)" >{{ value }}  </span>
            <span id="value" v-else  ><a :href="value">  {{ value }} </a> </span>

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
    },
    strip(str) {
        this.str  = str;
        var pattern = new RegExp('^(http?:\\/\\/)?'+ // protocol
        '((([a-z\\d]([a-z\\d-]*[a-z\\d])*)\\.)+[a-z]{2,}|'+ // domain name
        '((\\d{1,3}\\.){3}\\d{1,3}))'+ // OR ip (v4) address
        '(\\:\\d+)?(\\/[-a-z\\d%_.~+]*)*'+ // port and path
        '(\\?[;&a-z\\d%_.~+=-]*)?'+ // query string
        '(\\#[-a-z\\d_]*)?$','i'); // fragment locator
        return !!pattern.test(this.str);
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