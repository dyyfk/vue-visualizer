<template>
  <v-card>
    <v-card-title>
      <h3 class="headline">{{itemsToCompare.movie_title}}</h3>
    </v-card-title>
    <v-card-text id="card-contents">
      <ul>
        <li v-for="(value, index) in movie" :key="`value-${index}`">{{ index }} : {{ value }}</li>
        <li>
          <a v-bind:href="movie.movie_imdb_link">Sample link</a>
        </li>
      </ul>
    </v-card-text>
    <v-card-actions>
      <v-btn flat color="orange">Compare</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: ["itemsToCompare"]
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
</style>
