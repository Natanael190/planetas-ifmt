<!-- src/components/PlanetInfo.vue -->
<template>
  <div>
    <h4>Informações Adicionais</h4>
    <p><strong>Distância do Sol:</strong> {{ planet.distanceFromSun }} milhões de km</p>
    <p><strong>Número de Luas:</strong> {{ planet.numberOfMoons }}</p>
  </div>
</template>

<script>
export default {
  name: 'PlanetInfo',
  props: {
    planet: Object
  }
};
</script>

<style>
h4 {
  margin-top: 10px;
}
</style>
