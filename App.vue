<script>
import CommentList from './components/CommentList.vue';

export default {
  components: {
    CommentList
  }
};
</script>

<template>
  <div id="app">
    <h1>comment system</h1>
    <CommentList />
  </div>
</template>

<style>
#app {
  font-family: 'Arial', sans-serif;
  text-align: center;
  background-color: #f2f2f2;
  padding: 20px;
  min-height: 100vh;
}

h1 {
  font-size: 36px;
  color: #333;
  margin-bottom: 20px;
}
</style>
