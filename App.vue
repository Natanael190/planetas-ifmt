<template>
  <div>
    <h1>Planetas do Sistema Solar</h1>
    <PlanetList />
  </div>
</template>

<script>
import PlanetList from "./components/PlanetList.vue";

export default {
  name: "App",
  components: {
    PlanetList,
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  padding: 20px;
  background-color: #1E0ED3;
}

h1,
h2 {
  color: #333;
}
</style>
