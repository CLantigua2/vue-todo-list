<template>
  <div class="todo-item" v-bind:class="{'is-complete': todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button @click="$emit('edit-todo', todo.id, todo.title)" class="edit">Edit</button>
      <button @click="$emit('del-todo', todo.id)" class="del">Delete</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 10px;
  margin: 0 5px;
  cursor: pointer;
  float: right;
}
.edit {
  background: green;
  color: #fff;
  border: none;
  padding: 5px 9px;
  margin: 0 5px;
  border-radius: 10px;
  cursor: pointer;
  float: right;
}
</style>
