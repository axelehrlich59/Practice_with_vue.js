<template>
  <div class="container_components">
    <Counter />
    <Todo />
  </div>
</template>

<script>
import Counter from "./components/Counter.vue"
import Todo from "./components/Todo.vue"
export default {
  name: 'App',
  components: {
    Counter, 
    Todo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container_components {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
</style>
