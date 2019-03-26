<template>
  <div id="app">
    <Header v-on:createTodo="createTodo"/>
    <Todos v-bind:todos="todos" v-on:removeTodo="removeTodo"/>
  </div>
</template>



<script>
import Header from "./components/Header.vue";
import Todos from "./components/Todos.vue";
import { log } from "util";

let todos = [
  {
    id: "1",
    name: "Do the laundry",
    done: false
  },
  {
    id: "2",
    name: "Watch TV",
    done: false
  },
  {
    id: "3",
    name: "Write some code",
    done: false
  },
  {
    id: "4",
    name: "Clean my closet",
    done: false
  },
  {
    id: "5",
    name: "Resume work",
    done: false
  }
];

export default {
  name: "app",
  components: {
    Header,
    Todos
  },
  data: function() {
    return {
      todos: todos
    };
  },
  methods: {
    createTodo: function(todo) {
      let todoObject = {
        id: Math.floor(Math.random * 10000),
        name: todo,
        done: false
      };

      this.todos.push(todoObject);
    },
    removeTodo: function(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }
};
</script>



<style>
body {
  margin: 0;
  padding: 0;
  background-color: #ccc9c9;

  font-family: Arial, Helvetica, sans-serif;
}
</style>
