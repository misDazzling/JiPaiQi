<template>
  <div id="app">
    <CardRecorder /> <!-- 或 <CardRecorder /> -->
  </div>
</template>

<script>
import CardRecorder from './components/CardRecorder.vue'; //

export default {
  name: 'App',
  components: {
    CardRecorder, // 或 CardRecorder
  },
};
</script>