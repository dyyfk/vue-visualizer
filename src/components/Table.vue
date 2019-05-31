<template>
  <v-data-table :headers="headers" :items="desserts" class="elevation-1">
    <!-- <template slot="headers" slot-scope="props">
      <tr v-bind:key="props.index">
        <th v-for="header in props.headers">{{header.text}}</th>
      </tr>
    </template>-->

    <template v-slot:items="props">
      <tr>
        <td>{{ props.item.movie_title }}</td>
        <td
          class="text-xs-left"
          v-bind:class="compareRow(props.item,'color')"
        >{{ props.item.color }}</td>
        <td
          class="text-xs-left"
          v-bind:class="compareRow(props.item,'director_name')"
        >{{ props.item.director_name }}</td>
        <td
          class="text-xs-left"
          v-bind:class="compareRow(props.item,'num_critic_for_reviews')"
        >{{ props.item.num_critic_for_reviews }}</td>
        <td
          class="text-xs-left"
          v-bind:class="compareRow(props.item,'duration')"
        >{{ props.item.duration }}</td>
        <td
          class="text-xs-left"
          v-bind:class="compareRow(props.item,'director_facebook_likes')"
        >{{ props.item.director_facebook_likes }}</td>
      </tr>
    </template>
  </v-data-table>
</template>
<script>
export default {
  name: "Table",
  props: ["diffOnly"],
  data() {
    return {
      //   todos: [],
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
      ],
      desserts: [
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
        // {
        //   name: "Eclair",
        //   calories: 262,
        //   fat: 16.0,
        //   carbs: 23,
        //   protein: 6.0,
        //   iron: "7%"
        // }
        // {
        //   name: "Cupcake",
        //   calories: 305,
        //   fat: 3.7,
        //   carbs: 67,
        //   protein: 4.3,
        //   iron: "8%"
        // },
        // {
        //   name: "Gingerbread",
        //   calories: 356,
        //   fat: 16.0,
        //   carbs: 49,
        //   protein: 3.9,
        //   iron: "16%"
        // },
        // {
        //   name: "Jelly bean",
        //   calories: 375,
        //   fat: 0.0,
        //   carbs: 94,
        //   protein: 0.0,
        //   iron: "0%"
        // },
        // {
        //   name: "Lollipop",
        //   calories: 392,
        //   fat: 0.2,
        //   carbs: 98,
        //   protein: 0,
        //   iron: "2%"
        // },
        // {
        //   name: "Honeycomb",
        //   calories: 408,
        //   fat: 3.2,
        //   carbs: 87,
        //   protein: 6.5,
        //   iron: "45%"
        // },
        // {
        //   name: "Donut",
        //   calories: 452,
        //   fat: 25.0,
        //   carbs: 51,
        //   protein: 4.9,
        //   iron: "22%"
        // },
        // {
        //   name: "KitKat",
        //   calories: 518,
        //   fat: 26.0,
        //   carbs: 65,
        //   protein: 7,
        //   iron: "6%"
        // }
      ]
    };
  },

  methods: {
    compareRow(item, attr) {
      return this.desserts[0][attr] == this.desserts[1][attr] ? "green" : "red";
    },
    showDiff() {
      console.log(this.diffOnly);
    }
    // compareMean(item, attr) {
    //   let sum = this.desserts
    //     .map(dessert => dessert[attr])
    //     .reduce((p, c) => p + c);
    //   let mean = sum / this.desserts.length;
    //   return item[attr] > mean ? "green" : "red";
    // }
  },
  created() {}
};
</script>

<style>
</style>
