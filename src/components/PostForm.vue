<template>
  <form @submit.prevent>
    <h1>Создание поста</h1>
    <MyInput v-model:value="post.title" type="text" placeholder="Название"/>
    <MyInput v-model:value="post.body" type="text" placeholder="Текст"/>
    <MyButton class="btn_createPost" @click="createPost">Создать</MyButton>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton";
import MyInput from "@/components/UI/MyInput";
let id = 0;
export default {
  name: "PostForm",
  components: {MyInput, MyButton},
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = id+=1
      this.post.date = `${Date().slice(4,24)}`;
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    },
  }
}
</script>

<style scoped>

form {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
}

.btn_createPost{
  margin-top: 10px;
  color: teal;
  background-color: transparent;
  border: 1px solid teal;
  align-self: flex-end;
  padding: 10px 15px;
}
.btn_createPost:hover {
  transition-delay: 0.1s;
  background-color: ghostwhite;
  transform: scale(101%);
  cursor: pointer;
}

</style>