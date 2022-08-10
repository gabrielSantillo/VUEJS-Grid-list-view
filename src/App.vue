<template>
  <div id="app">

   <tweet-section></tweet-section>

  </div>
</template>

<script>

import TweetSection from '@/components/TweetSection.vue'

export default {
  name: 'App',
  components: {
    TweetSection
  }
}
</script>

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
