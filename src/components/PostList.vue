<template>
  <div v-if="posts.length > 0">
    <h3>Post list</h3>
    <transition-group name="post-list">
      <post-item v-for="post in posts" :key="post.id" :post="post" @remove-post="$emit('remove-post', post)"/>
    </transition-group>
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
.post-list-item {
  transition: all 0.8s ease;
  display: inline-block;
  margin-right: 10px;
}

.post-list-enter-from,
.post-list-leave-to {
  opacity: 0;
  transform: translateY(30px);
}

.post-list-leave-active {
  transition: all is ease;
}

</style>