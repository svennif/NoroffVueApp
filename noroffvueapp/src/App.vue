<template>
  <div id="app">
    <Recipe :title="recipes" />
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
  components: {
    Recipe,
  }, // components
  created: function () {
    const url = "http://www.recipepuppy.com/api/";
    const proxyUrl = "https://cors-anywhere.herokuapp.com/";

    fetch(proxyUrl + url)
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        this.recipes = JSON.stringify(data.results[0]);
        console.log(data.results);
      })
      .catch((error) => {
        console.log("Error: ", error);
      });
  }, // fetch function
}; // default
</script>