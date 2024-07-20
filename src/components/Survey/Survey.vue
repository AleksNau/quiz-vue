<script setup>

const {quizdata} = defineProps({
  quizdata:{
    type:Object,
  },
  typename:{
    type:String,
  }
})
</script>


<template>
    <div class="survey">
      <div v-if=" typename === 'words'">
        <p class="survey__question">{{ quizdata.question }}</p>
        <ul class="survey__list survey__list-words" v-if=" typename === 'words'">
          <li class="survey__answer-words survey__answer-info" v-for="t in quizdata.answers" :key="t.id">
            <input  class="answer__radio" type="radio"/>
            <span class="answer__text">{{t}}</span></li>
        </ul>
      </div>

      <div v-if=" typename === 'colors'">
        <p class="survey__question">{{ quizdata.question }}</p>
        <ul class="survey__list survey__list-colors" v-if=" typename === 'colors'">
          <li class="survey__answer-colors" :style="{ 'background-color': t}" v-for="t in quizdata.answers" :key="t.id">
          </li>
        </ul>
      </div>

      <div v-if=" typename === 'image'">
        <p class="survey__question survey__question-image">{{ quizdata.question }}</p>
        <img class="survey__image" :src="quizdata.image" alt="">
        <ul class="survey__list survey__list-images">
          <li class="survey__answer-images"  v-for="t in quizdata.answers" :key="t.id"><span class="answer__text answer__text-image">{{t}}</span>
          </li>
        </ul>
      </div>

      <div v-if=" typename === 'semiImage'">
        <p class="survey__question survey__question-figure">{{ quizdata.question }}</p>
        <img class="survey__image" :src="quizdata.image"  alt="">
        <ul class="survey__list survey__list-figure">
          <li class="survey__answer-words survey__answer-figure" v-for="t in quizdata.answers" :key="t.id">
            <input  class="answer__radio" type="radio"/>
            <span class="answer__text">{{t}}</span></li>
        </ul>
      </div>
    </div>
  </template>

  <style>

  .survey__question {
    font-family: PT Serif;
    font-size: 20px;
    line-height: 26.5px;
    letter-spacing: 0.05em;
    text-align: center;
    padding-top: 28px;
    max-width: 280px;
    margin: 0 auto;
  }

  .survey__question-figure {
    font-size: 16px;
    line-height: 21.2px;
  }

  .survey__question-image {
    max-width: 289px;
  }
  .survey__list {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  .survey__list-colors {
    display: flex;
    flex-wrap: wrap;
    gap: 23px 21px;
    padding: 20px 26px 34px 27px ;
  }
  .survey__answer-words {
    color: #FFF;
    display: flex;
    align-items: center;
    gap: 14px;
    background: rgba(242, 243, 243, 0.15);
    padding-left: 35px;
    height: 78px;
  }

  .survey__answer-info {
    height: 40px;
    gap: 39px;
    justify-content: normal;
  }

  .survey__answer-figure {
    justify-content: left;
    height: 50px;
  }

  .survey__list-images {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    padding: 23px 19px 35px 19px;
    max-width: 289px;
    margin: 0 auto;
    justify-content: space-between;
  }

  .survey__list-words {
    display: flex;
    flex-direction: column;
    padding: 30px 0 50px 0;
    gap: 19px;
  }

  .survey__list-figure {
    display: flex;
    flex-direction: column;
    padding: 19px 0 30px 0;
    gap: 8px;
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
    line-height: 20px;
    letter-spacing: 0.05em;
    text-align: left;
  }

  .survey__answer-colors {
    width: 75px;
    height: 75px;
  }

  .survey__image {

    display: block;
    margin: 30px auto 0 auto;
  }

  .survey__answer-images {
    width: 41px;
    height: 44px;
    background-color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .answer__text-image {
    color: #0f172a;

  }
  </style>