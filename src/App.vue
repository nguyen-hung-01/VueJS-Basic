<script setup>
import { ref } from 'vue'
import Lab1 from './components/Lab1/Lab1.vue'
import Lab2 from './components/Lab2/Lab2.vue'
import Lab3 from './components/Lab3/Lab3.vue'
import Lab4 from './components/Lab4/Lab4.vue'
import Lab5 from './components/Lab5/Lab5.vue'
import Lab6 from './components/Lab6/Lab6.vue'
import Lab7 from './components/Lab7/Lab7.vue'
const currentPage = ref('home')
</script>

<template>
  <nav>
    <ul>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'home'"
          :class="{ active: currentPage === 'home' }"
          >WEB2072</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab1'"
          :class="{ active: currentPage === 'lab1' }"
          >Lab 1</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab2'"
          :class="{ active: currentPage === 'lab2' }"
        >
          Lab 2</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab3'"
          :class="{ active: currentPage === 'lab3' }"
        >
          Lab 3</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab4'"
          :class="{ active: currentPage === 'lab4' }"
        >
          Lab 4</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab5'"
          :class="{ active: currentPage === 'lab5' }"
        >
          Lab 5</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab6'"
          :class="{ active: currentPage === 'lab6' }"
        >
          Lab 6</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab7'"
          :class="{ active: currentPage === 'lab7' }"
        >
          Lab 7</a
        >
      </li>
      <li>
        <a
          href="#"
          @click.prevent="currentPage = 'lab8'"
          :class="{ active: currentPage === 'lab8' }"
        >
          Lab 8</a
        >
      </li>
    </ul>
  </nav>
  <div id="main">
    <div class="content">
      <div class="home" v-if="currentPage === 'home'">
        <h1>WEB2072</h1>
        <h2>VueJS Basic</h2>
      </div>
      <Lab1 v-if="currentPage === 'lab1'" />
      <Lab2 v-if="currentPage === 'lab2'" />
      <Lab3 v-if="currentPage === 'lab3'" />
      <Lab4 v-if="currentPage === 'lab4'" />
      <Lab5 v-if="currentPage === 'lab5'" />
      <Lab6 v-if="currentPage === 'lab6'" />
      <Lab7 v-if="currentPage === 'lab7'" />
    </div>
  </div>
</template>

<style scoped>
#main {
  width: 1280px;
  margin: auto;
}
nav {
  position: fixed;
  z-index: 111111;
  top: 20px;
  left: 20px;
  padding: 25px 5px;
  background-color: rgb(35, 35, 35);
  border-radius: 7px;
}
nav li a {
  display: inline-block;
  width: 100%;
  color: #fff;
  cursor: pointer;
  padding: 10px 5px;
  margin: 5px 0;
  font-size: 16px;
  font-weight: 500;
  text-align: center;
  transition: 0.2s ease;
}
nav li:first-child a {
  padding: 20px 5px;
}
nav li a:hover {
  color: black;
  background-color: rgb(0, 229, 255);
}
nav li a.active {
  font-weight: bold;
  color: black;
  background-color: rgb(0, 229, 255);
}
.content {
  box-shadow: 0 0 15px #dcdcdc;
  width: 100%;
  min-height: 101vh;
  margin-bottom: 50px;
}
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background-color: black;
}
.home h1 {
  font-size: 40px;
  color: #fff;
}
.home h2 {
  font-size: 60px;
  font-weight: 800;
  color: green;
  text-shadow:
    0 0 2px rgb(5, 255, 5),
    0 0 70px rgb(0, 255, 0),
    0 0 15px rgb(45, 255, 45);
}
</style>
