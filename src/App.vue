<script setup>
import { ref } from 'vue'

let tasks = ['Learn Vue 3', 'Learn Vite', 'Build something awesome!']
let selectedTask = ref('nici un task selectat')
let showLogin = ref(true)

const selectTask = (task) => {
  selectedTask.value = task
  console.log(selectedTask)
}

const toggleShowLogin = () => {
  showLogin.value = !showLogin.value
}
</script>

<template>
  <h1>First VUE app!</h1>
  <ul id="ul">
    <li v-for="task of tasks" v-bind:key="task" @click="selectTask(task)">{{ task }}</li>
  </ul>
  <p>Task-ul selectat este: {{ selectedTask }}</p>

  <button @click="toggleShowLogin" v-if="showLogin">login</button>
  <button @click="toggleShowLogin" v-else>logout</button>
</template>

<style scoped></style>
