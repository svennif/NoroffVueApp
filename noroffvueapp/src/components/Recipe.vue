<template>
  <div>
    <ul class="test" v-for="(item, i) in title" :key="i">
      <li>{{ item.title }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Recipe",
  props: ["title"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
