<template>
  <div class="addTodo">
    <input
      type="text"
      v-bind:value="newTodo"
      v-on:input="$emit('input', $event.target.value)"
      placeholder="Add new task.."
    >
    <button @click="$emit('add-todo')" class="add">+</button>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  props: ["newTodo"]
};
</script>

<style scoped>
.addTodo {
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
  margin: 20px 0;
}
input {
  padding: 10px;
  width: 90%;
  border: 1px solid lightblue;
  border-top: 0;
  border-left: 0;
  border-right: 0;
  transition: 0.3s ease-in-out;
}
input:focus {
  outline: 0;
  border-bottom: 2px solid blue;
  margin-bottom: -1px;
}
.add {
  background: blue;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>

