<!-- src/components/PlanetQuiz.vue -->
<template>
  <div>
    <h4>Quiz sobre {{ planet.name }}</h4>
    <div v-if="currentQuestion < questions.length">
      <p>{{ questions[currentQuestion].question }}</p>
      <ul>
        <li v-for="(answer, index) in questions[currentQuestion].answers" :key="index">
          <button @click="checkAnswer(index)">{{ answer }}</button>
        </li>
      </ul>
      <p v-if="showFeedback">{{ feedbackMessage }}</p>
    </div>
    <div v-else>
      <p>Quiz concluído! Você acertou {{ correctAnswers }} de {{ questions.length }} perguntas.</p>
      <button @click="resetQuiz">Reiniciar Quiz</button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'PlanetQuiz',
  props: {
    planet: Object,
    questions: Array
  },
  setup(props) {
    const currentQuestion = ref(0);
    const correctAnswers = ref(0);
    const showFeedback = ref(false);
    const feedbackMessage = ref('');

    const checkAnswer = (index) => {
      if (index === props.questions[currentQuestion.value].correct) {
        correctAnswers.value++;
        feedbackMessage.value = 'Correto!';
      } else {
        feedbackMessage.value = 'Errado!';
      }
      showFeedback.value = true;
      setTimeout(() => {
        currentQuestion.value++;
        showFeedback.value = false;
      }, 1000);
    };

    const resetQuiz = () => {
      currentQuestion.value = 0;
      correctAnswers.value = 0;
    };

    return {
      currentQuestion,
      correctAnswers,
      showFeedback,
      feedbackMessage,
      checkAnswer,
      resetQuiz
    };
  }
};
</script>

<style>
button {
  margin: 5px;
}
</style>
