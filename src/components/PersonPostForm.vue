<script setup lang="ts">
import { computed } from '@vue/reactivity';
import { ref } from 'vue'

const inputtingName = ref<string>('')
const inputtingAge = ref<number>(0)

const emit = defineEmits(['register'])

const register = () => {
  const person = { id: Math.random(), name: inputtingName, age: inputtingAge.value }
  emit('register', person)
}

const nameLengthLimit = 15
const isValidName = computed((): boolean => {
  return inputtingName.value.length < 15
})
const color = computed((): string => {
  return isValidName.value ? 'white' : 'red'
})
</script>

<template>
  <div class="form-container">
    <div class="input-container">
      <div class="input-column">
        <span>name:</span>
        <input class="input-name" v-model="inputtingName" />
      </div>
      <span v-if="!isValidName" class="error-message">{{ nameLengthLimit }} characters or les, please</span>
      <div class="input-column">
        <span>age:</span>
        <input class="input" v-model="inputtingAge" type="number" />
      </div>
    </div>
    <button :disabled="!isValidName" class="register-button" @click="register">register</button>
  </div>
</template>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: lightblue;
  padding: 24px 0;
  width: 50%;
  margin-bottom: 12px;
  border-radius: 4px;
}

.input-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 50px;
  margin-bottom: 20px;
}

.input-column {
  width: 200px;
  display: flex;
  justify-content: space-between;
}

input {
  width: 120px;
  margin-bottom: 8px;
}

.input-name {
  background-color: v-bind(color);
}

.error-message {
  font-size: 12px;
  color: red;
}

span {
  font-size: 20px;
  font-weight: bold;
}
</style>