<template>
  <div class="container">
    <Header title="Task Tracker Vue App" />
    <Tasks :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data() {
    return {
      tasks: []
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'June 12th at 3pm',
        reminder: true,
      },
      {
        id: 2,
        text: 'Meeting with friends',
        day: 'June 15th at 5pm',
        reminder: true,
      },
      {
        id: 3,
        text: 'Visiting family',
        day: 'June 21st at 11:30am',
        reminder: false,
      }
    ]
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
