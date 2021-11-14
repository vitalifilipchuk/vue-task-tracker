<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
        <div class="task__head">
            <h3>{{task.text}}</h3>
            <svg @click="$emit('delete-task', task.id)" class="task__delete" xmlns="http://www.w3.org/2000/svg" fill="#000000" viewBox="0 0 50 50" width="20px" height="20px"><path d="M 9.15625 6.3125 L 6.3125 9.15625 L 22.15625 25 L 6.21875 40.96875 L 9.03125 43.78125 L 25 27.84375 L 40.9375 43.78125 L 43.78125 40.9375 L 27.84375 25 L 43.6875 9.15625 L 40.84375 6.3125 L 25 22.15625 Z"/></svg>
        </div>
        <p>{{task.day}}</p>
    </div>
    
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object
    },
}
</script>

<style>
 .task {
     margin: 5px;
     background-color: #f1f1f1;
     padding: 10px 15px;
     border-left: 5px solid transparent;
 }

 .reminder {
     border-left: 5px solid green;
 }

 .task__head {
     display: flex;
     align-items: center;
     justify-content: space-between;
 }

 .task__delete {
     cursor: pointer;
     fill: red;
 }
</style>