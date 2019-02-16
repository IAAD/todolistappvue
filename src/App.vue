<template>
  <div>
    <TodoList v-bind:todos="todos" />
    <!-- <CreateTodo v-on:add-todo="addTodo" /> -->
    <CreateTodo v-on:create-todo="addTodo" />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import CreateTodo from "./components/CreateTodo.vue";

export default {
  name: "app",
  components: {
    TodoList,
    CreateTodo
  },
  data() {
    return {
      todos: [
        {
          title: "First Todo",
          project: "Project 1",
          done: false
        },
        {
          title: "Second Todo",
          project: "Project 2",
          done: true
        },
        {
          title: "Third Todo",
          project: "Project 3",
          done: false
        }
      ]
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
