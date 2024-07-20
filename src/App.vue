<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/quiz">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<script setup>

</script>
<style scoped>

</style>
