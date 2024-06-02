<!-- src/components/Planet.vue -->
<template>
  <li @click="() => $emit('click', planet)">
    {{ planet.name }}
  </li>
</template>

<script>
export default {
  name: "Planet",
  props: {
    planet: Object,
  },
};
</script>

<style>
li {
  cursor: pointer;
  margin: 10px 0;
}
</style>
