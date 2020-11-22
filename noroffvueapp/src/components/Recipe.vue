<template>
  <div id="app">
    <ul class="recipe-title" v-for="(item, i) in recipes" : key="i">
      <li>{{ item.title }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Recipe",
  props: {
    msg: String,
    title: String
  } // props
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
