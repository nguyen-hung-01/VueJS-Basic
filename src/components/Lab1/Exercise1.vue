<script setup>
import { ref } from 'vue'

let check = ref(true)
let greeting = ref('')

const changeGreeting = () => {
  greeting.value = check.value ? 'Xin chào bạn!' : 'Hello World'
  check.value = !check.value
}
</script>

<template>
  <div class="exercise1">
    <h1>Change Content</h1>
    <button @click="changeGreeting">Nhấn để thay đổi lời chào</button>
    <p>{{ greeting }}</p>
  </div>
</template>

<style scoped>
.exercise1 {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
p {
  margin-top: 40px;
  font-size: 40px;
}
</style>
