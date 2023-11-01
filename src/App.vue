<template>
  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list
        :posts="posts"
        @remove="removePost"
    />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
export default {
  components: {
    PostForm,PostList
  },

  data () {
    return{
      posts:[
        {id:1, title: 'Название', body: 'Контент поста'},
        {id:2, title: 'Название 2', body: 'Контент поста 2'}
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p !== post.id)
    }
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.app{
  max-width: 1440px;
  margin: 0 auto;
}


</style>