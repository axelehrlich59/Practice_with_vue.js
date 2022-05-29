<template>
  <div class="container_todo">
    <h1 class="totolist_title">Todolist</h1>
    <hr class="separation_title_content" />
    <div class="input_container">
      <form @submit.prevent="addTodo">
        <input class="input_text" type="text" name="text" id="text" v-model="todoItem">
        <button class="button_submit" type="submit" @click="addTodo">Ajouter</button>
      </form>
    </div>
    <div class="todo_items_container">
      <li>Test</li>
    </div>
  </div>
</template>

<script>
import {ref} from "vue"
export default {
  setup(props, context) {
    let todoItem = ref("")

    const addTodo = () => {
      if(todoItem.value === "") return;
      console.log('todoItem ===== ', todoItem.value)
      context.emit("add", todoItem.value)
      todoItem.value = ""
    }

    return {
      todoItem,
      addTodo,
    }
  }
}
</script>

<style>
.container_todo {
  width: 80%;
  height: 500px;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  border-radius: 5px;
  margin-top: 50px;
}

.totolist_title {
  font-weight: lighter;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.separation_title_content {
  width: 50%;
  margin-bottom: 25px;
}

.input_container {
  margin-bottom: 45px;
}

.input_text {
  width: 30%;
  height: 30px;
  border-width: 1.5px;
  border-radius: 3px;
  font-size: 15px;
}

.button_submit {
  width: 80px;
  height: 30px;
  font-size: 15px;
  background-color: white;
  border: 1.5px solid black;
  border-radius: 3px;
  margin-left: 10px;
  cursor: pointer;
}

.button_submit:hover {
  opacity: 0.7;
  background-color: black;
  color: white;
  transition: 0.2s;
}
.todo_items_container {
  display: flex;
  flex-direction: column;
}



</style>