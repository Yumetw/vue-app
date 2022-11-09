<template>
  <div class="app">
    <PostForm
        @create="createPost"
    />
    <PostList
        :posts="posts"
        @delete="deletePost"
    />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  name: "App",
  components: {PostList, PostForm},
  data() {
      return {
       posts: [],
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post)
      },
      deletePost(post) {
        this.posts = this.posts.filter(val => val.id !== post.id)
      }
    }
  }
</script>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  opacity: 0;
  animation: present 0.5s forwards;
}
@keyframes present {
  0% {opacity: 0;}
  100% {opacity: 1;}
}

.app {
  padding: 20px;
}



</style>