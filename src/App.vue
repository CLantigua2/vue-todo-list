<template>
  <div id="app">
    <Header v-bind:header="header"/>
    <Todos v-bind:todos="todos" @del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Header";
export default {
  name: "app",
  components: {
    Todos,
    Header
  },
  // state
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ],
      header: "Todo App"
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(item => item.id !== id);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
#app {
  max-width: 500px;
  width: 500px;
  margin: 0 auto;
}
</style>
