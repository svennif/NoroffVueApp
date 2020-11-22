<template>
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <div class="card">
            <img class="img-fluid card-img-top" v-bind:src="recipe.thumbnail" alt="thumbnail of recipe"/>
            <div class="card-body">
            <h1 class="card-title">{{ recipe.title }}</h1>
            <p class="card-text">{{ recipe.ingredients }}</p>
            <a class="card-text">{{ recipe.href }}</a>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: "Recipe",
  props: ["recipe"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .container {
    margin: 20px;
    display: block;
  }
</style>
