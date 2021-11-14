<template>
    <form @submit="onSubmit" class="form add-form">
        <div class="form-control">
            <label for="">Task</label>
            <input type="text" v-model="text" name="text" placeholder="Add Task">
        </div>
        <div class="form-control">
            <label for="">Day & Time</label>
            <input type="text" v-model="day" name="day" placeholder="Add Day & Time">
        </div>
        <div class="form-control form-control-check">
            <label for="">Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder">
        </div>
        <input type="submit" value="Save Task" class="btn btn--block">
    </form>
</template>

<script>
export default {
    name: 'AddTask',
    data() {
        return {
            text: '',
            day: '',
            reminder: false
        }
    },
    methods: {
        onSubmit(e) {
            e.preventDefault();

            if (!this.text) {
                alert('Add a task first!')
                return
            }

            const newTask = {
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }

            this.text = ''
            this.day = ''
            this.reminder = false

            this.$emit('add-task', newTask)
        }
    }
}
</script>

<style scoped>
.add-form {
    margin-bottom: 30px;
}

.form-control {
    margin-bottom: 15px;
}

.form-control label {
    display: block;
    line-height: 1.5;
    font-size: 16px;
    font-weight: 600;
}

.form-control input {
    width: 100%;
    height: 40px;
    margin: 5px 0;
    padding: 3px 7px;
    font-size: 17px;
}
.form-control-check {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.form-control-check label {
    flex: 1;
}
.form-control-check input {
    flex: 2;
    height: 20px;
}
</style>