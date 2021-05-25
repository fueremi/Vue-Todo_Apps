<template>
  <header>
    <hr>
    <img alt="Vue logo" src="@/assets/logo.png" />
    <h1 class="mb-3">{{ title }}</h1>
    <ButtonComponent
      :title="showAddTask ? 'Close' : 'Add Task'"
      :background="showAddTask ? 'Salmon' : '#465EFC'"
      color="#FFF"
      @toggle-add-task="$emit('toggle-add-task')"
    />
  </header>
</template>

<script>
import ButtonComponent from "@/components/ButtonComponent";

export default {
  name: "HeaderComponent",
  props: ["title", "showAddTask"],
  components: {
    ButtonComponent,
  },
};
</script>

<style scoped>
h1 {
  font-weight: 300;
}
</style>