<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <input
        v-model="post.title"
        class="input"
        type="text" placeholder="Название">
    <input
        v-model="post.body"

        class="input"
        type="text" placeholder="Описание">
    <button class="btn">Create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      }
    }
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  border: 3px solid teal;
  margin-top: 15px;
  padding: 10px 15px;
  color: aliceblue;
}

input::placeholder {
  color: aliceblue;
}

form {
  display: flex;
  flex-direction: column;

}

.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  color: aliceblue;
  border: 3px solid teal;
  background-color: grey;
}

.btn:hover {
  background-color: darkorange;
}
</style>