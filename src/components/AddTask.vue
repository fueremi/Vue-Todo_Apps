<template>
  <div class="container">
    <hr />
    <h5>Add Task</h5>
    <form class="row" @submit.prevent="onSubmit()">
      <div class="col-md-5 mb-3">
        <label for="staticEmail2" class="visually-hidden">Email</label>
        <input
          type="text"
          class="form-control"
          id="title"
          placeholder="Task title (eg. Belajar Javascript)"
          v-model="title"
        />
      </div>
      <div class="col-md-5 mb-3">
        <label for="inputPassword2" class="visually-hidden">Date Time</label>
        <input
          type="text"
          class="form-control"
          id="datetime"
          placeholder="Date Time (eg. 12.00 AM, Monday)"
          v-model="datetime"
        />
      </div>
      <div class="col-md-2">
        <button type="submit" class="btn btn-primary">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      id: 8,
      title: '',
      datetime: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(){
      const newTask = {
        id: this.id,
        title: this.title,
        datetime: this.datetime,
        reminder: false
      }
      
      this.$emit('add-task', newTask)

      this.title = ''
      this.datetime= ''
    }
  }
};
</script>

<style scoped>
h5 {
  font-weight: 300;
}
</style>