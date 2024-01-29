<script>
export default {
  name: "my-button"
}
</script>

<template>
  <button class="btn">
    <slot name="button-name"></slot>
  </button>
</template>

<style scoped>
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  color: aliceblue;
  border: 3px solid teal;
  background-color: brown;
}

.btn:hover {
  background-color: darkorange;
}
</style>