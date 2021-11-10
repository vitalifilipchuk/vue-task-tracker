<template>
  <div class="container">
    <Header title="Task Tracker Vue App" />
  </div>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Helvetica, sans-serif;
}

#app {
  margin-top: 30px;
}

.container {
  max-width: 600px;
  padding: 0 30px;
  margin: 0 auto;
}

.btn {
  display: inline-block;
  text-align: center;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 5px;
  color: #fff;
  font-size: 15px;
}

btn:focus {
  outline: none;
}
</style>
