<template>

  <v-app>
    <v-content>
      <Table v-bind:file="file" v-model = "file" v-on:preview-row="previewRow"/>
      <v-layout row wrap> 
        <v-flex grow pa-1>
          <Card v-bind:itemsToCompare="itemsToCompare[0]" class="cards"/>
        </v-flex>
        <v-flex grow pa-1>
          <Card v-bind:itemsToCompare="itemsToCompare[1]" class="cards"/>
        </v-flex>
      </v-layout>
    </v-content>
    <Dialog v-bind:row="row" v-on:add-row="addRow"/>
  </v-app>
</template>


<script>
import Card from "./components/Card";
import Dialog from "./components/Dialog.vue";
import Table from "./components/Table";
import * as Papa from 'papaparse';


//import { watch } from 'fs';
//import { PerformanceObserver } from 'perf_hooks';

export default {
  name: "App",
  //props: ["row"],
  components: {
    Card,
    Dialog,
    Table
  },
  methods: {
    previewRow(row) {
      this.row = row;
    },
    addRow(row) {
      if (!this.leftAdded) {
        this.itemsToCompare.splice(0, 1, row);
        this.leftAdded = true;
      } else {
        this.itemsToCompare.splice(1, 1, row);
        this.leftAdded = false;
      }
    },
    loadFile() {
      if (!this.fileurl) {
        console.log("file is null; refusing to do anything");
        return;
      }
      console.log("first trial")
      let that = this;
      Papa.parse(this.fileurl,{
          download : true,
          header: true,
          complete: function(results) {
               //console.log("Help I am getting called!", results.data);
               //a = results;
               //this.file = results.data;
               that.file = results.data;
               //console.log("results", results);
           },

      });
   
    }
  },
  data: function() {
   //console.log("ajsdf")
   return {
      row:{},
      leftAdded:false,
      itemsToCompare:[{},{}],
      file: [ ],
      fileurl: "./data.csv"
    };
  },
  mounted() {
    this.loadFile();
  },
  watch:{
    fileurl(){
      this.loadFile();
    },
  }







};
</script>

<style>
  body {
    background: rgb(131,58,180);
    background: linear-gradient(90deg, rgba(131,58,180,1) 0%, rgba(253,29,29,1) 50%, rgba(252,176,69,1) 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    line-height: 1.4;
    color: #2c0938;
    font-family: 'Signika', sans-serif;
  }
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h1,
h2 {
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





