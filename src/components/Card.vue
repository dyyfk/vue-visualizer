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
        <!-- <span id="index">{{ index }}:</span>
        <span id="value"> {{ value }}</span> -->
          <span id="index">{{ index }}</span> :
          <span id="value" v-if = "!strip(this.value)" >{{ value }}  </span>
          <span id="value" v-else  ><a :href="value">  {{ value }} </a> </span>
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
  methods: {

  strip(str) {
        this.str = str;
        var pattern = new RegExp('^(http?:\\/\\/)?'+ // protocol
        '((([a-z\\d]([a-z\\d-]*[a-z\\d])*)\\.)+[a-z]{2,}|'+ // domain name
        '((\\d{1,3}\\.){3}\\d{1,3}))'+ // OR ip (v4) address
        '(\\:\\d+)?(\\/[-a-z\\d%_.~+]*)*'+ // port and path
        '(\\?[;&a-z\\d%_.~+=-]*)?'+ // query string
        '(\\#[-a-z\\d_]*)?$','i'); // fragment locator
        return !!pattern.test(this.str);
  }



  }
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
