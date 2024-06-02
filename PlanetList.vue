<!-- src/components/PlanetList.vue -->
<template>
  <div>
    <h2>Selecione um Planeta:</h2>
    <ul>
      <Planet
        v-for="planet in planets"
        :key="planet.name"
        :planet="planet"
        @click="handlePlanetClick(planet)"
      />
    </ul>
    <PlanetDetails v-if="selectedPlanet" :planet="selectedPlanet" />
  </div>
</template>

<script>
import { ref } from 'vue';
import Planet from './Planet.vue';
import PlanetDetails from './PlanetDetails.vue';

export default {
  name: 'PlanetList',
  components: {
    Planet,
    PlanetDetails
  },
  setup() {
    const planets = ref([
      { 
        name: 'Mercúrio', 
        details: 'Mercúrio é o menor planeta do sistema solar.', 
        image: '/src/assets/mercury.jpeg', 
        distanceFromSun: 57.9, 
        numberOfMoons: 0,
        questions: [
          {
            question: 'Qual é a posição de Mercúrio em relação ao Sol?',
            answers: ['Primeiro', 'Segundo', 'Terceiro'],
            correct: 0
          }
        ]
      },
      { 
        name: 'Vênus', 
        details: 'Vênus é o segundo planeta do sistema solar.', 
        image: '/src/assets/venus.jpeg', 
        distanceFromSun: 108.2, 
        numberOfMoons: 0,
        questions: [
          {
            question: 'Qual é a temperatura média em Vênus?',
            answers: ['467°C', '200°C', '750°C'],
            correct: 0
          }
        ]
      },
      { 
        name: 'Terra', 
        details: 'Terra é o terceiro planeta do sistema solar e o único habitado.', 
        image: '/src/assets/earth.jpg', 
        distanceFromSun: 149.6, 
        numberOfMoons: 1,
        questions: [
          {
            question: 'Quantas luas a Terra possui?',
            answers: ['1', '2', '3'],
            correct: 0
          }
        ]
      },
      { 
        name: 'Marte', 
        details: 'Marte é conhecido como o planeta vermelho.', 
        image: '/src/assets/mars.jpg', 
        distanceFromSun: 227.9, 
        numberOfMoons: 2,
        questions: [
          {
            question: 'Quantas luas tem Marte?',
            answers: ['1', '2', '3'],
            correct: 1
          }
        ]
      },
      { 
        name: 'Júpiter', 
        details: 'Júpiter é o maior planeta do sistema solar.', 
        image: '/src/assets/jupiter.jpg', 
        distanceFromSun: 778.3, 
        numberOfMoons: 79,
        questions: [
          {
            question: 'Qual planeta é conhecido como o gigante gasoso?',
            answers: ['Júpiter', 'Saturno', 'Netuno'],
            correct: 0
          }
        ]
      },
      { 
        name: 'Saturno', 
        details: 'Saturno é conhecido pelos seus anéis impressionantes.', 
        image: '/src/assets/saturn.png', 
        distanceFromSun: 1427, 
        numberOfMoons: 82,
        questions: [
          {
            question: 'Qual planeta tem anéis impressionantes?',
            answers: ['Júpiter', 'Saturno', 'Urano'],
            correct: 1
          }
        ]
      },
      { 
        name: 'Urano', 
        details: 'Urano é um gigante gasoso com um eixo de rotação incomum.', 
        image: '/src/assets/uranus.jpg', 
        distanceFromSun: 2871, 
        numberOfMoons: 27,
        questions: [
          {
            question: 'Qual planeta tem um eixo de rotação incomum?',
            answers: ['Netuno', 'Urano', 'Saturno'],
            correct: 1
          }
        ]
      },
      { 
        name: 'Netuno', 
        details: 'Netuno é o planeta mais distante do Sol.', 
        image: '/src/assets/neptune.png', 
        distanceFromSun: 4495, 
        numberOfMoons: 14,
        questions: [
          {
            question: 'Qual é o planeta mais distante do Sol?',
            answers: ['Urano', 'Netuno', 'Plutão'],
            correct: 1
          }
        ]
      },
      { 
        name: 'Plutão', 
        details: 'Plutão é um planeta anão no cinturão de Kuiper.', 
        image: '/src/assets/pluto.png', 
        distanceFromSun: 5906, 
        numberOfMoons: 5,
        questions: [
          {
            question: 'Quantas luas Plutão possui?',
            answers: ['3', '5', '7'],
            correct: 1
          }
        ]
      }
    ]);

    const selectedPlanet = ref(null);

    const handlePlanetClick = (planet) => {
      selectedPlanet.value = planet;
    };

    return {
      planets,
      selectedPlanet,
      handlePlanetClick
    };
  }
};
</script>

<style>
ul {
  padding: 0;
  list-style: none;
}

li {
  cursor: pointer;
  margin: 10px 0;
}
</style>
