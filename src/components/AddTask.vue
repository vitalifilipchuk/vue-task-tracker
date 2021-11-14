<template>
    <form action="" class="form add-form">
        <div class="form-control">
            <label for="">Task</label>
            <input type="text" name="text" placeholder="Add Task">
        </div>
        <div class="form-control">
            <label for="">Day & Time</label>
            <input type="text" name="day" placeholder="Add Day & Time">
        </div>
        <div class="form-control form-control-check">
            <label for="">Set Reminder</label>
            <input type="checkbox" name="reminder">
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
    margin: 5px;
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