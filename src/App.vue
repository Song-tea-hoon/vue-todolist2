<template>
  <div id="app">
    <TodoList/>
  </div>
</template>

<script>
import './assets/css/common.css'
import TodoList from './components/TodoList'

export default {
  name: 'app',
  components: {
    TodoList
  }
}
</script>

<style>

</style>
