<template>
  <div class="app">
    <h1>{{ message }}</h1>
    <button @click="count++">Count is: {{ count }}</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello Vue with Vanilla JS!',
      count: 0
    }
  }
}
</script>

<style>
.app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}
button {
  padding: 10px 20px;
  font-size: 16px;
}
</style>