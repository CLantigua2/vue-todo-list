<template>
  <div id="app">
    <Header v-bind:header="header"/>
    <FilterSearch v-model="search"/>
    <Todos v-bind:todos="filteredTodos" @del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Header";
import FilterSearch from "./components/FilterSearch";
export default {
  name: "app",
  components: {
    Todos,
    Header,
    FilterSearch
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
      search: ""
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(item => item.id !== id);
    },
    inputChange() {
      this.todos =
        this.todos.filter(todo =>
          todo.toUpperCase().indexOf(this.search.toUpperCase())
        ) > -1;
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
