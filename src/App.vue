<template>
  <div id="app">
    <h1>当前时间：{{ currentTime }}</h1>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      currentTime: this.getCurrentTime()
    }
  },
  mounted() {
    this.startTime();
  },
  methods: {
    getCurrentTime() {
      return new Date().toLocaleTimeString();
    },
    startTime() {
      this.currentTime = this.getCurrentTime();
      setInterval(() => {
        this.currentTime = this.getCurrentTime();
      }, 1000);
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
</style>
