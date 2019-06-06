<template>
  <v-card>
    <v-card-title primary-title></v-card-title>
    {{itemsToCompare.movie_title}}
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

<style>
</style>
