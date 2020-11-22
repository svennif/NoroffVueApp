<template>
  <div id="app">
    <Recipe msg="This is a title" />
  </div>
</template>

<script>
import Recipe from "./components/Recipe.vue";

export default {
  name: "App",
  data() {
    return {
      recipes: [],
    }; // return
  }, // data
  created: function () {
    const url = "http://www.recipepuppy.com/api/";
    const proxyUrl = "https://cors-anywhere.herokuapp.com/";

    fetch(proxyUrl + url)
      .then((response) => response.json())
      .then((response) => {
        console.log(response.results);
      })
      .catch((error) => {
        console.log('Error: ', error);
      });
  }, // fetch function
  components: {
    Recipe,
  }, // components
}; // default
</script>

<style></style>