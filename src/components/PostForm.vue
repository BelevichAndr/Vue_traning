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
    <my-button
        class="btn"
        @click="createPost"
    >
      Create
    </my-button>


Aa2706002000

  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton"
export default {
  components: {MyButton},
  data() {
    return {
      post: {
        title: "",
        body: "",
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: "",
        body: "",
      }
      this.title = ""
      this.body = ""
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

</style>