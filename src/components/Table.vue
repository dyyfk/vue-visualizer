<template>
  <div>
    <v-checkbox v-model="checkbox" label="Only show the difference"></v-checkbox>
    <v-data-table :headers="headers" :items="movies" class="elevation-1">
      <template slot="items" slot-scope="props">
        <tr @click="select(props.item)">
          <td>{{ props.item.movie_title }}</td>
          <td class="text-xs-left">{{ props.item.color }}</td>
          <td class="text-xs-left">{{ props.item.director_name }}</td>
          <td class="text-xs-left">{{ props.item.num_critic_for_reviews }}</td>
          <td class="text-xs-left">{{ props.item.duration }}</td>
          <td class="text-xs-left">{{ props.item.director_facebook_likes }}</td>
        </tr>
      </template>
    </v-data-table>
    <Dialog/>
  </div>
</template>
<script>
import loadedJson from "../assets/test.json"

export default {
  name: "Table",
  props: ["movies"],
  data() {
    return {
      checkbox: false,
      headers: [
        {
          text: "movie_title",
          align: "left",
          sortable: false,
          value: "name"
        },
        { text: "color", value: "color" },
        { text: "director_name", value: "director_name" },
        { text: "num_critic_for_reviews", value: "num_critic_for_reviews" },
        { text: "duration", value: "duration" },
        { text: "director_facebook_likes", value: "director_facebook_likes" }
      ]
    };
  },

  methods: {
    select(row) {
      this.$emit("preview-row", row);
    }
  },
  created() {}
};
</script>

<style>
</style>
