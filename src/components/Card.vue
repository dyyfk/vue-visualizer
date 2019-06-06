<template>
  <v-layout>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
        <v-card-title primary-title>
          <div>
            <div>
              <h3 class="headline mb-0">{{ movie.movie_title }}</h3>
              <strong>{{movie.director_name}}</strong>
            </div>
            <a v-bind:href="movie.movie_imdb_link">link</a>
          </div>
        </v-card-title>

        <v-card-actions>
          <v-btn flat color="orange">Compare</v-btn>\
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      movie: {
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
        movie_imdb_link: "http://www.imdb.com/title/tt0499549/?ref_=fn_tt_tt_1",
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
      }
    };
  }
};
</script>

<style>
</style>
