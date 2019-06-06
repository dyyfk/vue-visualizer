<template>
  <v-app>
    <v-content>
      <Table v-bind:movies="movies" v-on:preview-row="previewRow"/>
      <Card/>
      <Dialog v-bind:row="row"/>
    </v-content>
  </v-app>
</template>

<script>
import Table from "./components/Table";
import Card from "./components/Card";
import Dialog from "./components/Dialog.vue";

export default {
  name: "App",
  components: {
    Table,
    Card,
    Dialog
  },
  methods: {
    previewRow(row) {
      this.row = row;
    }
  },
  data() {
    return {
      row: {},
      movies: [
        {
          color: "Color",
          director_name: "James Cameron",
          num_critic_for_reviews: 723,
          duration: 178,
          director_facebook_likes: 0,
          actor_3_facebook_likes: 855,
          actor_2_name: "Joel David Moore",
          actor_1_facebook_likes: 1000,
          gross: 760505847,
          genres: "Action|Adventure|Fantasy|Sci-Fi",
          actor_1_name: "CCH Pounder",
          movie_title: "Avatar",
          num_voted_users: 886204,
          cast_total_facebook_likes: 4834,
          actor_3_name: "Wes Studi",
          facenumber_in_poster: 0,
          plot_keywords: "avatar|future|marine|native|paraplegic",
          movie_imdb_link:
            "http://www.imdb.com/title/tt0499549/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 3054,
          language: "English",
          country: "USA",
          content_rating: "PG-13",
          budget: 237000000,
          title_year: 2009,
          actor_2_facebook_likes: 936,
          imdb_score: 7.9,
          aspect_ratio: 1.78,
          movie_facebook_likes: 33000
        },
        {
          color: "Color",
          director_name: "Gore Verbinski",
          num_critic_for_reviews: 302,
          duration: 169,
          director_facebook_likes: 563,
          actor_3_facebook_likes: 1000,
          actor_2_name: "Orlando Bloom",
          actor_1_facebook_likes: 40000,
          gross: 309404152,
          genres: "Action|Adventure|Fantasy",
          actor_1_name: "Johnny Depp",
          movie_title: "Pirates of the Caribbean: At World's End",
          num_voted_users: 471220,
          cast_total_facebook_likes: 48350,
          actor_3_name: "Jack Davenport",
          facenumber_in_poster: 0,
          plot_keywords:
            "goddess|marriage ceremony|marriage proposal|pirate|singapore",
          movie_imdb_link:
            "http://www.imdb.com/title/tt0449088/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 1238,
          language: "English",
          country: "USA",
          content_rating: "PG-13",
          budget: 300000000,
          title_year: 2007,
          actor_2_facebook_likes: 5000,
          imdb_score: 7.1,
          aspect_ratio: 2.35,
          movie_facebook_likes: 0
        }
      ]
    };
  }
};
</script>
