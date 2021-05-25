<template>
  <div class="container">
    <div class="row mt-4">
      <div class="col-md-3" v-for="task in tasks" :key="task.id">
        <Task :task="task" />
      </div>
    </div>
  </div>
</template>

<script>
import Task from '@/components/Task'

export default {
  name: "Tasks",
  props: {
    tasks: {
      type: Array,
    },
  },
  components: {
    Task,
  }
};
</script>

<style scoped>
p {
  text-align: justify !important;
}
</style>