<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'
type Tweet = {
  id: number,
  description: string,
}
type Props = {
  tweets: Tweet[]
}
defineProps<Props>()

const emit = defineEmits(['delete-tweet'])

const deleteTweet = (id: number) => {
  emit('delete-tweet', id)
}
</script>

<template>
  <ul>
    <li v-for="tweet in tweets" :key="tweet.id" class="tweet-list">
      <span>{{ tweet.description }}</span>
      <button class="delete-button" @click="deleteTweet(tweet.id)">delete</button>
    </li>
  </ul>
</template>

<style scoped>
.tweet-list {
  list-style: none;
  margin-bottom: 12px;
  border-radius: 4px;
  font-size: 12px;
  display: flex;
  justify-content: space-between;
  background-color: aliceblue;
  padding: 8px 20px;
  width: 300px;
}
</style>