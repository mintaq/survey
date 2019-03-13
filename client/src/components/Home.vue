<template>
  <v-container fluid grid-list-lg relative>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card>
          <v-card-title primary-title>
            <div>
              <div class="headline top">{{card_title}}</div>
              <div class="grey--text bot">{{card_text}}</div>
            </div>
          </v-card-title>

          <v-card-actions>
            <v-btn flat color="blue-grey">Share</v-btn>
            <v-btn flat color="blue-grey">Edit</v-btn>
            <v-btn flat color="blue-grey">Preview</v-btn>
            <v-btn flat color="blue-grey">Result</v-btn>
            <v-btn flat color="red">Delete</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
    <div class="text-xs-center">
      <v-btn v-show="!hidden" color="blue-grey" dark center fab>
        <v-icon>add</v-icon>
      </v-btn>
    </div>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    card_text: "Meow Meow Meow Meow Meow Meow Meow Meow ",
    card_title: "Survey Title",
    show: false
  })
};
</script>

<style scoped>
.survey-card {
  margin: 15px auto;
}
</style>

