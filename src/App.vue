<script setup lang="ts">
import { provide } from 'vue'
import { todos, todoKey } from './useTodo'
import Tweet from './components/Tweet.vue';
import Persons from './components/Persons.vue';
import Reservation from './components/Reservation.vue';
import TodoList from './components/TodoList.vue';
import Form from './components/Form.vue';

// provide('todos', todos)
provide(todoKey, todos)
</script>

<template>
  <!-- <Tweet /> -->
  <!-- <Persons /> -->
  <!-- <Reservation /> -->
  <!-- <TodoList /> -->
  <Form />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
