<script setup>
import { ref } from 'vue'
import Exercise1 from './Exercise1.vue'
import Exercise2 from './Exercise2.vue'
import ExtraExercises from './ExtraExercises.vue'

const currentPage = ref('exercise1')
</script>

<template>
  <div id="wrapper">
    <nav class="menu-top">
      <a
        href="#"
        @click.prevent="currentPage = 'exercise1'"
        :class="{ active: currentPage === 'exercise1' }"
        >Exercise 1</a
      >
      <a
        href="#"
        @click.prevent="currentPage = 'exercise2'"
        :class="{ active: currentPage === 'exercise2' }"
        >Exercise 2</a
      >
      <a
        href="#"
        @click.prevent="currentPage = 'extraExercises'"
        :class="{ active: currentPage === 'extraExercises' }"
        >Extra Exercises</a
      >
    </nav>
    <div class="content">
      <Exercise1 v-if="currentPage === 'exercise1'" />
      <Exercise2 v-if="currentPage === 'exercise2'" />
      <ExtraExercises v-if="currentPage === 'extraExercises'" />
    </div>
  </div>
</template>

<style scoped>
.content {
  display: flex;
  justify-content: center;
}
</style>
