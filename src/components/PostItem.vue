<template>
  <div class="post">
    <div class="post_id">{{ post.id }}</div>
    <div class="post_date">{{ post.date }}</div>
    <div class="post_title"><strong>Название:</strong> {{ post.title }}</div>
    <div class="post_body"><strong>Текст:</strong> {{ post.body }}</div>
    <MyButton class="btn_deletePost" @click="$emit('delete',post)">Удалить</MyButton>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
export default {
  name: "PostItem",
  components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>

.post_date, .post_id {
  display: inline-block;
}

.post {
  padding: 15px;
  border: 1px solid teal;
  margin-top: 15px;
  min-height: 130px;
  height: 100%;
  width: 100%;
}


.post_date {
  color: teal;
  font-size: 0.8em;
}

.post_id {
  color: teal;
  font-size: 0.8em;
  float: right;
}

.btn_deletePost {
  margin-top: 10px;
  color: teal;
  background-color: transparent;
  border: 1px solid teal;
  padding: 10px 15px;
  display: inline;
  float: right;
}

.btn_deletePost:hover {
  transition-delay: 0.1s;
  background-color: ghostwhite;
  transform: scale(101%);
  cursor: pointer;
}

</style>