<script>
import uniqueId from "lodash.uniqueid";
import TodoItem from './components/ToDoItem.vue'
import ToDoForm from "./components/ToDoForm.vue";

export default {
  name: 'app',
  components: {
    TodoItem,
    ToDoForm
  },
  data() {
    return {
      TodoItems: [
        {id: uniqueId('todo-'), label: 'Learn Vue1', done: false},
        {id: uniqueId('todo-'), label: 'Learn Vue2', done: true},
        {id: uniqueId('todo-'), label: 'Learn Vue3', done: true},
        {id: uniqueId('todo-'), label: 'Learn Vue4', done: false},
      ]
    }
  }
}


</script>

<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ul>
      <li>
        <ToDoForm></ToDoForm>
      </li>
      <li v-for="item in TodoItems" :key="item.id">
        <TodoItem :label="item.label" :id="item.id" :done="item.done"></TodoItem>
      </li>
      <li v-for="item in TodoItems" :key="item.id">
        <todo-item :label="item.label" :id="item.id" :done="item.done"></todo-item>
      </li>
    </ul>
  </div>
</template>

