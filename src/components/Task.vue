<template>
  <div class="list-group mb-1">
    <div
      href="#"
      :class="[
        task.reminder ? 'list-group-item-success' : 'list-group-item-primary',
        'list-group-item',
        'mb-3',
      ]"
      aria-current="true"
    >
      <div class="d-flex justify-content-between">
        <h5 class="mb-3 text-center">Task {{ task.id }}</h5>
        <div class="form-check form-switch">
          <input
            class="form-check-input"
            type="checkbox"
            id="flexSwitchCheckDefault"
            :checked="task.reminder"
            @change="$emit('toggle-reminder', task.id)"
          />
          <button class="btn m-0 p-0" @click="$emit('delete-task', task.id)">
            <b-icon icon="x-circle-fill"></b-icon>
          </button>
        </div>
      </div>
      <p class="mb-3 text-start">
        {{ task.title }}
      </p>
      <small> {{ task.datetime }}</small>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: {
      type: Object,
    },
  },
};
</script>

<style scoped>
svg {
  color: salmon;
}

.form-check-input:checked {
  background-color: #465efc;
  border-color: #465efc;
}
</style>