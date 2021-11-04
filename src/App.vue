<template>
  <div class="container">
    <Header />
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
</style>
