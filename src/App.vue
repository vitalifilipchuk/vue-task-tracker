<template>
  <div class="container">
    <Header 
    @toggle-add-form="toggleAddTask" 
    title="Task Tracker Vue App" 
    :showAddTask="showAddTask" />
    <router-view :showAddTask="showAddTask"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  },
  data() {
    return {
      
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    }
  },
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
  background: #000;
  color: #fff;
  font-size: 15px;
}

.btn--block {
  display: block;
  width: 100%;
}

btn:focus {
  outline: none;
}
</style>
