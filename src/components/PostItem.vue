<template>
  <div class="post ">
    <div>
      <div><strong>Название:</strong>{{ post.title }}</div>
      <div><strong>Описание:</strong>{{ post.body }}</div>
    </div>
    <div class="post__btns">
      <my-button @remove="$emit('remove', post)">
        Удалить
      </my-button>
    </div>

  </div>
</template>

<script>

export default {

  props: {
    post: {
      type: Object,
      required: true,
    }
  }
}
</script>

<style scoped>
.post{
  padding: 15px;
  border: 2px dotted #cf5353;
  margin: 15px auto;
  max-width: 500px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>