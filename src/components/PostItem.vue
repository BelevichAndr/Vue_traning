<template>
  <div class="post">

    <div>
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>

    <div class="post__buttons">
      <my-button @click="$emit('remove-post', post)">
        <template v-slot:button-name> Удалить </template>
      </my-button>
    </div>

  </div>
</template>

<script>

export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 3px solid teal;
  margin-top: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>