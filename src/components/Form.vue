<template>
  <v-container>
    <v-form ref="form" lazy-validation>
      <!-- <v-btn :disabled="!valid" color="success" @click="submit">Search</v-btn> -->
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: "Form",
  data: () => ({
    select: null,
    items: ["Item 1", "Item 2", "Item 3", "Item 4"],
    checkbox: false
  }),

  methods: {
    // diffOnly(e) {
    //   this.$emit("show-diff", e);
    // }
  }
};
</script>

<style scoped>
</style>
