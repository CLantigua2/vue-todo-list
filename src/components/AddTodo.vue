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
}
input {
  padding: 10px;
  width: 90%;
  border: 1px solid lightblue;
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

