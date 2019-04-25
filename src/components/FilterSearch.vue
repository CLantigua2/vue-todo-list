<template>
  <div class="search">
    <input
      class="searchInput"
      v-bind:value="search"
      v-on:input="$emit('input', $event.target.value)"
      placeholder="Search..."
    >
  </div>
</template>

<script>
export default {
  name: "FilterSearch",
  props: ["search"]
};
</script>

<style scoped>
.search {
  width: 100%;
  margin: 20px;
}
.search .searchInput {
  padding: 10px;
  width: 90%;
  border: 1px solid lightblue;
  border-top: 0;
  border-left: 0;
  border-right: 0;
  transition: 0.3s ease-in-out;
}
.searchInput:focus {
  outline: 0;
  border-bottom: 1px solid blue;
}
</style>
