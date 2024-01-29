<template>
  <form @submit.prevent>
    <h4>Create post</h4>

    <my-input v-model="post.title" type="text" placeholder="Название"/>

    <my-input v-model="post.body" type="text" placeholder="Описание"/>

    <my-button class="btn" @click="createPost" style="align-self: flex-end">
      <template v-slot:button-name> Сохранить </template>
    </my-button>

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


input::placeholder {
  color: aliceblue;
}

form {
  display: flex;
  flex-direction: column;

}

</style>