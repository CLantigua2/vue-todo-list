<template>
  <div id="app">
    <FilterSearch v-model="search"/>
    <Header v-bind:header="header"/>
    <AddTodo v-model="newTodo" @add-todo="addTodo"/>
    <Todos v-bind:todos="filteredTodos" @del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Header";
import FilterSearch from "./components/FilterSearch";
import AddTodo from "./components/AddTodo";
export default {
  name: "app",
  components: {
    Todos,
    Header,
    FilterSearch,
    AddTodo
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
      header: "Todo App",
      search: "",
      newTodo: ""
    };
  },
  methods: {
    deleteTodo() {
      this.todos = this.todos.filter(item => item.id !== id);
    },
    addTodo() {
      const currentId = this.todos.length;
      this.todos.push({
        id: currentId + 1,
        title: this.newTodo,
        completed: false
      });
      return (this.newTodo = "");
    }
  },
  computed: {
    filteredTodos() {
      return this.todos.filter(todo => {
        if (todo.title.toLowerCase().indexOf(this.search.toLowerCase()) > -1) {
          return todo;
        } else {
          return null;
        }
      });
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
