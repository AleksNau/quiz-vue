<script setup>
import Loader from "../../components/Loading/Loading.vue";

const {quizdata} = defineProps({
  quizdata: {
    type: Object,
  },
  typename: {
    type: String,
  },
  isLoading: {
    type: Boolean,
  }
})


</script>


<template>
  <div v-if="isLoading === true" class="survey">
    <div v-if=" typename === 'words'">
      <p class="survey__question">{{ quizdata.question }}</p>
      <ul v-if=" typename === 'words'" class="survey__list survey__list-words">
        <li v-for="(t, index) in quizdata.answers" :key="index">
          <input :id="index" class="survey__radio" name="radio-example" type="radio">
          <label :for="index" class="survey__label">{{ t }}
          </label></li>
      </ul>
    </div>

    <div v-if=" typename === 'colors'">
      <p class="survey__question">{{ quizdata.question }}</p>
      <ul v-if=" typename === 'colors'" class="survey__list survey__list-colors">
        <li v-for="(t, index) in quizdata.answers" :key="index" :style="{ 'background-color': t}">
          <input :id="index" class="survey__radio-colors" name="radio-example" type="radio">
          <label :for="index" :style="{ 'background-color': t}" class="survey__label-colors">
          </label>
        </li>
      </ul>
    </div>

    <div v-if=" typename === 'image'">
      <p class="survey__question survey__question-image">{{ quizdata.question }}</p>
      <img :src="quizdata.image" alt="" class="survey__image">
      <ul class="survey__list survey__list-images">
        <li v-for="(t, index) in quizdata.answers" :key="index" class="survey__answer-images">
          <input :id="index" class="survey__radio-images" name="radio-example" type="radio">
          <label :for="index" class="survey__label-images survey__text-image">{{ t }}
          </label>
        </li>
      </ul>
    </div>

    <div v-if=" typename === 'semiImage'">
      <p class="survey__question survey__question-figure">{{ quizdata.question }}</p>
      <img :src="quizdata.image" alt="" class="survey__image">
      <ul class="survey__list survey__list-figure">
        <li v-for="(t, index) in quizdata.answers" :key="index">
          <input :id="index" class="survey__radio" name="radio-example" type="radio">
          <label :for="index" class="survey__label">{{ t }}
          </label></li>
      </ul>
    </div>
  </div>
  <Loader v-else/>
</template>

<style>
@import 'Survey.css';
</style>