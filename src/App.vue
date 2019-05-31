<template>
  <v-app>
    <v-content>
      <Form v-on:show-diff="showDiff"/>
      <Table v-bind:diffOnly="diffOnly"/>
    </v-content>
  </v-app>
</template>

<script>
import Form from "./components/Form";
import Table from "./components/Table";
export default {
  name: "App",
  components: {
    Form,
    Table
  },
  methods: {
    showDiff(e) {
      return e;
    }
  },
  data() {
    return {
      diffOnly: false
    };
  }
};
</script>
