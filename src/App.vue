<template>
  <div class="container">
    <Header 
    @toggle-add-form="toggleAddTask" 
    title="Task Tracker Vue App" 
    :showAddTask="showAddTask" />
    <div v-if="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: [],
      showAddTask: false
    }
  },
  methods: {
    deleteTask(id) {
      if (confirm('Are you sure?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
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
