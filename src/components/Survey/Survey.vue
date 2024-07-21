<script setup>
import Loader from "../../components/Loading/Loading.vue";

const {quizdata} = defineProps({
  quizdata:{
    type:Object,
  },
  typename:{
    type:String,
  },
  isLoading:{
    type:Boolean,
  }
})


</script>


<template>
    <div class="survey" v-if="isLoading === true">
      <div v-if=" typename === 'words'">
        <p class="survey__question">{{ quizdata.question }}</p>
        <ul class="survey__list survey__list-words" v-if=" typename === 'words'">
          <li v-for="(t, index) in quizdata.answers" :key="index">
            <input type="radio" class="survey__radio" :id="index"  name="radio-example">
            <label class="survey__label" :for="index">{{t}}
            </label></li>
        </ul>
      </div>

      <div v-if=" typename === 'colors'">
        <p class="survey__question">{{ quizdata.question }}</p>
        <ul class="survey__list survey__list-colors" v-if=" typename === 'colors'">
          <li :style="{ 'background-color': t}" v-for="(t, index) in quizdata.answers" :key="index">
            <input type="radio" class="survey__radio-colors" :id="index"  name="radio-example">
            <label class="survey__label-colors"  :style="{ 'background-color': t}" :for="index">
            </label>
          </li>
        </ul>
      </div>

      <div v-if=" typename === 'image'">
        <p class="survey__question survey__question-image">{{ quizdata.question }}</p>
        <img class="survey__image" :src="quizdata.image" alt="">
        <ul class="survey__list survey__list-images">
          <li class="survey__answer-images"  v-for="(t, index) in quizdata.answers" :key="index">
            <input type="radio" class="survey__radio-images" :id="index"  name="radio-example">
            <label class="survey__label-images survey__text-image" :for="index">{{t}}
            </label>
          </li>
        </ul>
      </div>

      <div v-if=" typename === 'semiImage'">
        <p class="survey__question survey__question-figure">{{ quizdata.question }}</p>
        <img class="survey__image" :src="quizdata.image"  alt="">
        <ul class="survey__list survey__list-figure">
          <li v-for="(t, index) in quizdata.answers" :key="index">
            <input type="radio" class="survey__radio" :id="index"  name="radio-example">
            <label class="survey__label" :for="index">{{t}}
            </label></li>
        </ul>
      </div>
    </div>
  <Loader v-else/>
  </template>

  <style>
  @import 'Survey.css';
  </style>