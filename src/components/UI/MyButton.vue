<script>
</script>

<template>
  <button>
    <slot></slot>
  </button>
</template>

<style scoped>
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  color: aliceblue;
  border: 3px solid teal;
  background-color: grey;
}

.btn:hover {
  background-color: darkorange;
}
</style>