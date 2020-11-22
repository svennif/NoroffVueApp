<template>
  <div id="app">
    <ul class="recipe-title" v-for="(item, i) in recipes" : key="i">
      <li>{{ item.title }}</li>
    </ul>
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
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        this.recipes = data.results;
        console.log(data.results);
      })
      .catch((error) => {
        console.log("Error: ", error);
      });
  }, // fetch function
  components: {
    Recipe: Recipe,
  }, // components
}; // default
</script>