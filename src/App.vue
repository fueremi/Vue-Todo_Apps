<template>
  <div id="app">
    <HeaderComponent :showAddTask="showAddTask" title="Vue Todo Apps" @toggle-add-task="toggleAddTask"/>
    <AddTask v-if="showAddTask" @add-task="addTask"/>
    <hr>
    <Tasks
      :tasks="tasks"
      @toggle-reminder="toggleReminder"
      @delete-task="deleteTask"
    />
  </div>
</template>

<script>
import HeaderComponent from "@/components/HeaderComponent";
import Tasks from "@/components/Tasks";
import AddTask from "@/components/AddTask";

export default {
  name: "App",
  components: {
    HeaderComponent,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          title: "Belajar Vue",
          datetime: "08.30 AM, Monday",
          reminder: true,
        },
        {
          id: 2,
          title: "Belajar React",
          datetime: "08.30 AM, Tuesday",
          reminder: false,
        },
        {
          id: 3,
          title: "Belajar Angular",
          datetime: "08.30 AM, Wednesday",
          reminder: true,
        },
        {
          id: 4,
          title: "Belajar Express",
          datetime: "08.30 AM, Thursday",
          reminder: false,
        },
        {
          id: 5,
          title: "Belajar Laravel",
          datetime: "08.30 AM, Friday",
          reminder: false,
        },
        {
          id: 6,
          title: "Belajar Django",
          datetime: "08.30 AM, Saturday",
          reminder: false,
        },
        {
          id: 7,
          title: "Belajar Springboot",
          datetime: "08.30 AM, Sunday ",
          reminder: false,
        },
      ],
      showAddTask: false,
    };
  },
  methods: {
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id)
    },
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
    addTask(newTask){
      this.tasks.push(newTask)
    }
  },
};
</script>

<style>
#app {
  font-family: "Ubuntu";
  margin: 0;
  text-align: center;
}

.list-group-item-primary {
  color: #465efc !important;
  background-color: #e1e5ff !important;
  border-radius: 10px;
}

.list-group-item-success {
  color: rgb(34, 114, 47) !important;
  background-color: rgb(216, 247, 221) !important;
}
</style>
