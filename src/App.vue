<template>
  <div class="app">
    <h1>Страница с постами</h1>

    <div class="app__buttons">
      <my-button @click="showDialog">
        <template v-slot:button-name>
          Создать Пост
        </template>
      </my-button>
      <my-select v-model="selectedSort" :options="sortOptions"/>
    </div>


    <my-dialog v-model:is_show="dialogVisible">
      <post-form @create="createPost"/>
    </my-dialog>
    <post-list :posts="posts" @remove-post="removePost"/>
  </div>

</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import axios from 'axios'

export default {

  components: {
    PostList, PostForm
  },

  data() {
    return {
      posts: [],
      dialogVisible: false,
      selectedSort: "",
      sortOptions: [
        {value: "title", name: "По названию"},
        {value: "body", name: "По описанию"},
      ]
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
      this.dialogVisible = false
    },
    removePost(post) {
      this.posts = this.posts.filter(post_item => post_item.id !== post.id)
    },
    showDialog() {
      this.dialogVisible = true
    },
    async fetchPosts() {
      try {
        const response = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10")
        console.log(response)
        response.data.forEach(object => this.posts.push(object))
      } catch (error) {
        alert("Ошибка")
      }
    },
  },
  mounted() {
    this.fetchPosts()
  },
  watch: {
    selectedSort(newValue) {
      this.posts.sort((post1, post2) => {
        return post1[newValue].localeCompare(post2[newValue])
      })
    }
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

.app__buttons {
  display: flex;
  justify-content: space-between;
  margin: 15px 0
}

</style>