<template>

  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list
        :posts="posts"
    />
  </div>

</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {

  components: {
    PostList, PostForm
  },

  data() {
    return {
      posts: [
        {id: 1, title: "JS", body: `Описание поста 1`},
        {id: 2, title: "JS", body: `Описание поста 2`},
        {id: 3, title: "JS", body: `Описание поста 3`},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: darkslategrey;
}


.app {
  padding: 20px;
  color: aliceblue;

}

</style>