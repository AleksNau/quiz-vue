<script setup>

import {RouterView,useRouter} from 'vue-router'
import Burger from './components/Burger/Burger.vue'

const router = useRouter()

</script>

<template>
  <div class="container">
    <header>
      <div class="wrapper">
        <Burger/>
        <div v-if="router.currentRoute.value.path === '/quiz'" class="brain-container">
          <img alt="мозг" height="47" src="./assets/rain_bk3.png" width="48"/>
          <p  class="brain__title">тест на определение IQ</p>
        </div>
        <div v-if="router.currentRoute.value.path === '/result'" class="brain-container">
          <img alt="мозг" height="47" src="./assets/rain_bk3.png" width="48"/>
          <p class="brain__title brain__title-result">Готово!</p>
        </div>
      </div>
    </header>

    <RouterView/>
  </div>
</template>

<script setup>

</script>
<style scoped>
.brain-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
}

.brain__title {
  font-family: Yeseva One;
  font-size: 12px;
  line-height: 13.86px;
  letter-spacing: 0.05em;
  text-align: left;
  text-transform: uppercase;
  color: #FFC700;
}

.brain__title-result {
  font-size: 20px;
  line-height: 23.1px;
  letter-spacing: 0.1em;
}
</style>
