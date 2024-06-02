<!-- src/components/PlanetDetails.vue -->
<template>
  <div>
    <h3>Detalhes do Planeta:</h3>
    <img :src="planet.image" :alt="planet.name" width="100" />
    <p><strong>{{ planet.name }}:</strong> {{ planet.details }}</p>
    <PlanetInfo :planet="planet" />
    <PlanetQuiz :planet="planet" :questions="planet.questions" />
  </div>
</template>

<script>
import PlanetInfo from './PlanetInfo.vue';
import PlanetQuiz from './PlanetQuiz.vue';

export default {
  name: 'PlanetDetails',
  components: {
    PlanetInfo,
    PlanetQuiz
  },
  props: {
    planet: Object
  }
};
</script>

<style>
img {
  display: block;
  margin-bottom: 10px;
}
</style>
