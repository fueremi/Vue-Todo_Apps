<template>
  <header>
    <hr>
    <img alt="Vue logo" src="@/assets/logo.png" />
    <h1 class="mb-3">{{ title }}</h1>
    <Button
      :title="showAddTask ? 'Close' : 'Add Task'"
      :background="showAddTask ? 'Salmon' : '#465EFC'"
      color="#FFF"
      @toggle-add-task="$emit('toggle-add-task')"
    />
  </header>
</template>

<script>
import Button from "@/components/Button";

export default {
  name: "Header",
  props: ["title", "showAddTask"],
  components: {
    Button,
  },
};
</script>

<style scoped>
h1 {
  font-weight: 300;
}
</style>