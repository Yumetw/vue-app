<template>
  <PostItem
      v-for="post in posts"
      :post="post"
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

.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 15px;
  min-height: 130px;
  height: 100%;
  width: 100%;
}

</style>
