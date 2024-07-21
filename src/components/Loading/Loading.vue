<script setup>
import Spinner from '../Circle/Circle.vue'</script>


<template>
  <div class="loading">
    <p class="loading__title">Обработка результатов</p>
    <Spinner/>
    <p class="loading__text">Определение стиля мышления...........
      ........................................................</p>
  </div>
</template>
<style>

.loading {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.loading__title {
  font-family: PT Serif;
  padding-top: 49px;
  font-size: 23px;
  line-height: 30.47px;
  letter-spacing: 0.05em;
  text-align: center;
  max-width: 237px;
}

.loading__text {
  font-family: PT Serif;
  font-size: 14px;
  line-height: 18.55px;
  letter-spacing: 0.05em;
  text-align: left;
  max-width: 276px;
}


</style>