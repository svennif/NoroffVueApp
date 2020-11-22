<template>
  <div id="app">
    <recipe-list v-for="(x, i) in recipes" v-bind:key="i" v-bind:recipe="x"/>
  </div>
</template>

<script>
import Recipe from "./components/Recipe.vue";
import axios from 'axios';

export default {
  name: "App",
  data() {
    return {
      recipes: [],
    }; // return
  }, // data
  components: {
    "recipe-list": Recipe,
  }, // component
  created: function () {
    const url = "http://www.recipepuppy.com/api/";
    const proxyUrl = "https://cors-anywhere.herokuapp.com/";

    axios.get(proxyUrl + url) 
    .then(resp => {
      console.log(resp);
      this.recipes = resp.data.results;
    })
    .catch(err => {
      console.log(err);
    })

  }, // fetch function
}; // default
</script>