<template >
  <div class="quiz">
    <PBar :count="lengthItem" />
    <div class="container">

      <Survey :quizdata="quizdata[count]" :typename="quizdata[count].type"/>
      <button type="button" class="quiz__button" @click="makeProgress">далее</button>
    </div>
  </div>


</template>

<style>
.quiz {
  box-sizing:border-box ;
  background: url('../assets/quiz_bg.jpg')  no-repeat;
  min-height: 568px;
  padding: 17px 0 25px 0;
  position: relative;
}

.container {
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

}

.quiz__button{
  display: block;
  width: 189px;
  height: 41px;
  border-radius: 20px;
  font-family: Merriweather;
  font-size: 14px;
  text-transform: uppercase;
  line-height: 17.6px;
  letter-spacing: 0.1em;
  border: none;
  background: rgba(255, 255, 255, 1);
  color: rgba(142, 142, 142, 1);
  text-align: center;
  position: absolute;
  bottom: 23px;

  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
}

</style>

<script setup>
import Survey from "../components/Survey/Survey.vue";
import PBar from "../components/ProgressBar/ProgressBar.vue";
import {ref} from "vue";
let count = ref(0)

const quizdata = ref([
  { id: 1, answers: ['Мужчина','Женщина'], question: "ваш пол:",type:"words"},
  { id: 2, answers: ['До 18','От 18 до 28','от 29 до 35','От 36'], question: "укажите ваш возраст:" ,type:"words"},
  { id: 3, answers: ['Дом','Шалаш','Бунгало','Скамейка','Хижина'], question: "Выберите лишнее:",type:"words"},
  { id: 4, answers: [62,48,74,57,60,77], question: "Продолжите числовой ряд:18  20  24  32  :",type:"words"},
  { id: 5, answers: ['#A8A8A8','#0000A9','#00A701','#F60100','#FDFF19','#A95403','#000000','#850068','#46B2AC'], question: "Выберите цвет, который сейчас наиболее Вам приятен:",type:"colors"},
  { id: 6, answers: ['#A8A8A8','#46B2AC','#A95403','#00A701','#000000','#F60100','#850068','#FDFF19','#0000A9'], question: "Отдохните пару секунд, еще раз Выберите цвет, который сейчас наиболее Вам приятен:",type:"colors"},
  { id: 7, answers: ['Вашингтон','Лондон','Париж','Нью-Йорк','Москва','Оттава'], question: "Какой из городов лишний?",type:"words"},
  { id: 8, answers: [1,2,3,4], question: "Выберите правильную фигуру из четырёх пронумерованных.",image:"../../src/assets/questions/question8.jpg",type:"image"},
  { id: 9, answers: ['Наслаждаться каждой минутой проведенного времени','Быть устремленными мыслями в будущее','Учитывать в ежедневной практике прошлый опыт'], question: "Вам привычнее и важнее:",type:"words"},
  { id: 10, answers: ['оно остроконечное','оно устойчиво','оно-находится в состоянии равновесия'], question: "Какое определение, по-Вашему, больше подходит к этому геометрическому изображению: ",image:"../../src/assets/questions/question10.jpg" ,type:"semiImage"},
  { id: 11, answers: [34,36,53,44,66,42], question: "Вставьте подходящее число",image:"../../src/assets/questions/question11.jpg",type:"image"},
]);

let oneItem = 100/quizdata.value.length;
let lengthItem = ref(oneItem) ;
const makeProgress = () => {
  if(count.value < quizdata.value.length-1) {
    count.value ++;
    lengthItem.value += oneItem;
  }
  return null;
}
</script>
