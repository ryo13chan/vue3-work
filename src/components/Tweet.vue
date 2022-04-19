<script setup lang="ts">
import { ref } from 'vue'
import TweetPostFrom from './TweetPostFrom.vue';
import TweetList from './TweetList.vue';
const tweets = ref([
  { id: 0, description: 'Hello, world!', },
  { id: 1, description: 'this is the second tweet', },
])
const postTweet = (description: string) => {
  const tweet = { id: Math.random(), description }
  tweets.value.push(tweet)
}

const deleteTweet = (id: number) => {
  tweets.value = tweets.value.filter(t => t.id !== id)
}

</script>

<template>
  <div class="container">
    <h1>Tweeter</h1>
    <TweetPostFrom @post-tweet="postTweet" />
    <div class="tweet-containter">
      <p v-if="tweets.length <= 0">No tweets have been added</p>
      <TweetList :tweets="tweets" @delete-tweet="deleteTweet" />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>