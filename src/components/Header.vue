<template>
    <header>
        <h1>{{title}}</h1>
        <Button 
        @btn-click="$emit('toggle-add-form')" 
        :text="showAddTask ? 'Close' : 'Add Task'" 
        :color="showAddTask ? 'darkred' : 'green'"  />
    </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean,
    },
    components: {
        Button
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        align-self: start;
        margin-bottom: 20px;
    }
</style>