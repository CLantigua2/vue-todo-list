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
}
.search .searchInput {
  width: 100%;
  height: 25px;
  border: 1px solid lightblue;
  padding: 10px;
}
</style>
