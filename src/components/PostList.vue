<template>
  <div class="no-posts" v-if="posts.length === 0">
    Пока что тут пусто =(
  </div>
  <PostItem
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @delete="$emit('delete',post)"
  />
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  name: "PostList",
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>

.no-posts {
  color: lightgray;
  font-size: 1.3em;
  font-family: Bahnschrift,serif;
}

</style>
