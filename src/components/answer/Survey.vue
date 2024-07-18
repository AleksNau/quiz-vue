<script setup>
const props = defineProps({
  quizdata:{
    type:Array,
  }
})
</script>


<template>
    <div>
      <p class="survey__question">{{ quizdata.question }}</p>
      <ul class="survey__list">
        <li class="survey__answer" v-for="t in quizdata.answers" :key="t.id"><input class="answer__radio" type="radio"/>
          <span class="answer__text">{{t}}</span></li>
      </ul> 
    </div>
  </template>
  
  <style>
  .survey__question {
    font-family: PT Serif;
    font-size: 20px;
    line-height: 26.5px;
    letter-spacing: 0.05em;
    text-align: center;
    margin-bottom: 41px;
  }
  .survey__list {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  .survey__answer {
    color: #FFF;
    display: flex;
    align-items: center;
    gap: 39px;
    background: rgba(242, 243, 243, 0.15);
    padding-left: 35px;
  }

  .answer__radio {
    width: 20px;
    height: 20px;
    border: 1px solid #FFF;
    background-color:  rgba(28,28,28,0);
  }

  .answer__text {
    font-family: PT Serif;
    font-size: 18px;
    line-height: 58px;
    letter-spacing: 0.05em;
    text-align: left;
  }
  </style>