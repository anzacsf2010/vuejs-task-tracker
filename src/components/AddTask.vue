<template>
  <form class='add-form'>
    <div class='form-control'>
      <label>Task</label>
      <input type='text' name='text' v-model="text" placeholder='Add Task' />
    </div>
    <div class='form-control'>
      <label>Day & Time</label>
      <input type='text' name="day" v-model="day" placeholder='Add Day & Time' />
    </div>
    <div class='form-control form-control-check'>
      <label>Set Reminder</label>
      <input type='checkbox' name="reminder" v-model="reminder"/>
    </div>
    <input type='submit' value='Save Task' class='btn btn-block' @click="onSubmit"/>
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      text: '',
      day: '',
      reminder: false,
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.text) {
        alert('Please enter a task!');
        return
      }
      const newTask = {
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      }
      this.$emit('add-task',newTask);
      this.text = '';
      this.day = '';
      this.reminder = false;
    }
  },
  emits: ['add-task'],
}
</script>
