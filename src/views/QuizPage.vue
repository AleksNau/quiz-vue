<template>
  <div class="quiz">
    <PBar :count="lengthItem" />
    <Survey :quizdata="quizdata[count]"/>
    <button type="button" class="quiz__button" @click="makeProgress">далее</button>
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

</style>

<script setup>
import Survey from "../components/Survey/Survey.vue";
import PBar from "../components/ProgressBar/ProgressBar.vue";
import {ref} from "vue";
let count = ref(0)

const quizdata = ref([
  { id: 1, answers: ['Мужчина','Женщина'], question: "ваш пол:"},
  { id: 2, answers: ['До 18','От 18 до 28','от 29 до 35','От 36'], question: "укажите ваш возраст:" },
  { id: 3, answers: ['Дом','Шалаш','Бунгало','Скамейка','Хижина'], question: "Выберите лишнее:"},
]);

let oneItem = 100/quizdata.value.length;
let lengthItem = ref(0) ;
const makeProgress = () => {
  if(count.value < quizdata.value.length) {
    count.value ++;
    lengthItem.value += oneItem;
  }
  return null;
}
</script>
