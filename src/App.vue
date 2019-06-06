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
import Card from "./components/Card";
import Dialog from "./components/Dialog.vue";
import Table from "./components/Table";

export default {
  name: "App",
  components: {
    Card,
    Dialog,
    Table
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
        },
        {
          color: "Color",
          director_name: "Sam Mendes",
          num_critic_for_reviews: 602,
          duration: 148,
          director_facebook_likes: 0,
          actor_3_facebook_likes: 161,
          actor_2_name: "Rory Kinnear",
          actor_1_facebook_likes: 11000,
          gross: 200074175,
          genres: "Action|Adventure|Thriller",
          actor_1_name: "Christoph Waltz",
          movie_title: "Spectre",
          num_voted_users: 275868,
          cast_total_facebook_likes: 11700,
          actor_3_name: "Stephanie Sigman",
          facenumber_in_poster: 1,
          plot_keywords: "bomb|espionage|sequel|spy|terrorist",
          movie_imdb_link:
            "http://www.imdb.com/title/tt2379713/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 994,
          language: "English",
          country: "UK",
          content_rating: "PG-13",
          budget: 245000000,
          title_year: 2015,
          actor_2_facebook_likes: 393,
          imdb_score: 6.8,
          aspect_ratio: 2.35,
          movie_facebook_likes: 85000
        },
        {
          color: "Color",
          director_name: "Christopher Nolan",
          num_critic_for_reviews: 813,
          duration: 164,
          director_facebook_likes: 22000,
          actor_3_facebook_likes: 23000,
          actor_2_name: "Christian Bale",
          actor_1_facebook_likes: 27000,
          gross: 448130642,
          genres: "Action|Thriller",
          actor_1_name: "Tom Hardy",
          movie_title: "The Dark Knight Rises",
          num_voted_users: 1144337,
          cast_total_facebook_likes: 106759,
          actor_3_name: "Joseph Gordon-Levitt",
          facenumber_in_poster: 0,
          plot_keywords:
            "deception|imprisonment|lawlessness|police officer|terrorist plot",
          movie_imdb_link:
            "http://www.imdb.com/title/tt1345836/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 2701,
          language: "English",
          country: "USA",
          content_rating: "PG-13",
          budget: 250000000,
          title_year: 2012,
          actor_2_facebook_likes: 23000,
          imdb_score: 8.5,
          aspect_ratio: 2.35,
          movie_facebook_likes: 164000
        },
        {
          color: "",
          director_name: "Doug Walker",
          num_critic_for_reviews: "",
          duration: "",
          director_facebook_likes: 131,
          actor_3_facebook_likes: "",
          actor_2_name: "Rob Walker",
          actor_1_facebook_likes: 131,
          gross: "",
          genres: "Documentary",
          actor_1_name: "Doug Walker",
          movie_title: "Star Wars: Episode VII - The Force Awakens",
          num_voted_users: 8,
          cast_total_facebook_likes: 143,
          actor_3_name: "",
          facenumber_in_poster: 0,
          plot_keywords: "",
          movie_imdb_link:
            "http://www.imdb.com/title/tt5289954/?ref_=fn_tt_tt_1",
          num_user_for_reviews: "",
          language: "",
          country: "",
          content_rating: "",
          budget: "",
          title_year: "",
          actor_2_facebook_likes: 12,
          imdb_score: 7.1,
          aspect_ratio: "",
          movie_facebook_likes: 0
        },
        {
          color: "Color",
          director_name: "Andrew Stanton",
          num_critic_for_reviews: 462,
          duration: 132,
          director_facebook_likes: 475,
          actor_3_facebook_likes: 530,
          actor_2_name: "Samantha Morton",
          actor_1_facebook_likes: 640,
          gross: 73058679,
          genres: "Action|Adventure|Sci-Fi",
          actor_1_name: "Daryl Sabara",
          movie_title: "John Carter",
          num_voted_users: 212204,
          cast_total_facebook_likes: 1873,
          actor_3_name: "Polly Walker",
          facenumber_in_poster: 1,
          plot_keywords: "alien|american civil war|male nipple|mars|princess",
          movie_imdb_link:
            "http://www.imdb.com/title/tt0401729/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 738,
          language: "English",
          country: "USA",
          content_rating: "PG-13",
          budget: 263700000,
          title_year: 2012,
          actor_2_facebook_likes: 632,
          imdb_score: 6.6,
          aspect_ratio: 2.35,
          movie_facebook_likes: 24000
        },
        {
          color: "Color",
          director_name: "Sam Raimi",
          num_critic_for_reviews: 392,
          duration: 156,
          director_facebook_likes: 0,
          actor_3_facebook_likes: 4000,
          actor_2_name: "James Franco",
          actor_1_facebook_likes: 24000,
          gross: 336530303,
          genres: "Action|Adventure|Romance",
          actor_1_name: "J.K. Simmons",
          movie_title: "Spider-Man 3",
          num_voted_users: 383056,
          cast_total_facebook_likes: 46055,
          actor_3_name: "Kirsten Dunst",
          facenumber_in_poster: 0,
          plot_keywords: "sandman|spider man|symbiote|venom|villain",
          movie_imdb_link:
            "http://www.imdb.com/title/tt0413300/?ref_=fn_tt_tt_1",
          num_user_for_reviews: 1902,
          language: "English",
          country: "USA",
          content_rating: "PG-13",
          budget: 258000000,
          title_year: 2007,
          actor_2_facebook_likes: 11000,
          imdb_score: 6.2,
          aspect_ratio: 2.35,
          movie_facebook_likes: 0
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1, h2 {
  font-weight: normal;
}
a {
  color: #42b983;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>

