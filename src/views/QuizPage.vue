<template>
  <div class="quiz">
    <progress class="quiz__progressbar" value="70" max="100">70 %</progress>
    <Survey :quizdata="quizdata[count]"/>
    <button class="quiz__button">далее</button>
  </div>
</template>

<style>
.quiz {
  background: url('../assets/quiz_bg.jpg') no-repeat;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 568px;
  padding: 17px 0 25px 0;
}

.quiz__button{
  display: block;
  width: 189px;
  height: 41px;
  border-radius: 20px;
  font-family: Merriweather;
  font-size: 14px;
  line-height: 17.6px;
  letter-spacing: 0.1em;
  text-align: center;
  margin: 0 auto;
}

.quiz__progressbar {
  min-width: 200px;
  margin: 0 auto;
}

</style>

<script setup>
import Survey from "../components/answer/Survey.vue";
import {ref,computed} from "vue";

let count = 0;
const quizdata = ref([
  { id: 1, answers: ['Мужчина','Женщина'], question: "ваш пол:"},
  { id: 2, answers: ['До 18','От 18 до 28','от 29 до 35','От 36'], question: "укажите ваш возраст:" },
  { id: 3, answers: ['Дом','Шалаш','Бунгало','Скамейка','Хижина'], question: "Выберите лишнее:"},
]);
</script>
