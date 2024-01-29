<template>
  <div v-if="posts.length > 0">
    <h3>Post list</h3>
    <post-item v-for="post in posts" :key="post.id" :post="post" @remove-post="$emit('remove-post', post)"/>
  </div>

</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  components: {PostItem},

  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>
<style scoped>

</style>