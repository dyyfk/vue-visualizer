<template>
  <div>
    <v-checkbox v-model="checkbox" label="Only show the difference"></v-checkbox>
    <v-data-table :headers="iheaders" :items="dataarray" class="elevation-1">
      <template slot="items" slot-scope="props">
        <tr @click="select(props.item)"> 
          <!-- <td>{{ props.item.Title }}</td> 
          <td>{{ props.item.Year }}</td>  -->
          <td class="text-xs-left" v-for="(value, index) in iheaders" 
          :key="`value-${index}`" >
            {{props.item[value.value]}} 
            <!-- {{"test"+index}} -->
          </td>

          
          <!-- <td v-for = "head in file" >{{  file[Title]      }}  </td> -->
          <!-- <td class="text-xs-left">{{ props.item.color }}</td> 
          <td class="text-xs-left">{{ props.item.director_name }}</td>
          <td class="text-xs-left">{{ props.item.num_critic_for_reviews }}</td>
          <td class="text-xs-left">{{ props.item.duration }}</td>
          <td class="text-xs-left">{{ props.item.director_facebook_likes }}</td> --> 
      
       </tr>
      </template>
    </v-data-table>
    <Dialog/>
  </div>
</template>
<script>
//import loadedJson from "../assets/test.json";

export default {
  name: "Table",
  props: ["dataarray","iheaders"],
  data() {
    return {
      checkbox: false,
      //headers: this.iheaders
      // headers: [
      //   {
      //     text: "conference_title",
      //     align: "left",
      //     sortable: false,
      //     value: "name"
      //   },
        

      //   // { text: "year", value: "year" },

      //   // { text: "color", value: "color" },
      //   // { text: "director_name", value: "director_name" },
      //   // { text: "num_critic_for_reviews", value: "num_critic_for_reviews" },
      //   // { text: "duration", value: "duration" },
      //   // { text: "director_facebook_likes", value: "director_facebook_likes" }
      // ]
    };
  },
  mounted() {
    console.log(this.iheaders);
  },
  watch: {
    iheaders(){ 
      console.log(this.iheaders);
    }
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
