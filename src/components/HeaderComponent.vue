<template>
  <header>
    <img alt="Vue logo" src="@/assets/logo.png">
    <h1 class="mb-3">{{ title }}</h1>
    <hr>
    <ButtonComponent title="Add Task" background="#465EFC" color="#FFF"/>
  </header>
</template>

<script>
import ButtonComponent from '@/components/ButtonComponent'

export default {
  name: 'HeaderComponent',
  props: ['title'],
  components: {
    ButtonComponent,
  }
};
</script>

<style scoped>
h1 {
  font-weight: 300;
}
</style>