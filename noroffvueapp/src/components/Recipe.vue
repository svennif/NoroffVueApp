<template>
  <div>
    <ul class="recipe" v-for="(item, i) in thisIsAtest" :key="i">
      <li>
        <div>{{ item[i].title }}</div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Recipe",
  props: ['thisIsAtest'],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.recipe {
  margin: 0;
  padding: 0;
  list-style-type: none;
  margin: 10px 5%;
  font: 1.5rem;
}
</style>
