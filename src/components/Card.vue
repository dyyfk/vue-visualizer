<template>
  <v-card>
    <v-card-title>
      <h3 class="headline">{{itemsToCompare.movie_title}}</h3>
    </v-card-title>
    <v-card-text id="card-contents">
      <ul>
        <li
          v-for="(value, index) in itemsToCompare"
          :key="`value-${index}`"
        >
        <span id="index">{{ index }}:</span>
        <span id="value"> {{ value }}</span>
        </li>
      </ul>
    </v-card-text>
    <v-card-actions>
      <v-btn round color="primary" dark>Compare</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: ["itemsToCompare"],
  methods: {}
};
</script>

<style scoped>
v-card {
  margin: 10px;
}
#card-contents {
  text-align: left;
  
}
a {
  color: #42b983;

}
#index {
  color: #42b983;
  font-weight: bold;
}
li {
  padding: 10px;
}
</style>
