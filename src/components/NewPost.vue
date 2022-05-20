<template>
  <div class="posts">
    <h1>Add Note</h1>
      <div class="form">
        <div>
          <input type="text" name="title" placeholder="TITLE" v-model="title">
        </div>
        <div>
          <textarea rows="15" cols="15" placeholder="DESCRIPTION" v-model="description"></textarea>
        </div>
        <div>
          <button class="app_post_btn" @click="addPost">+ Add Note</button>
        </div>
      </div>
  </div>
</template>

<script>
import PostsService from '/SRL-WebApp/posts/client/src/services/PostService'
export default {
  name: 'NewPost',
  // returns data, title and description
  data () {
    return {
      title: '',
      description: ''
    }
  },
  // method that access the post service in order to create the note
  methods: {
    async addPost () {
      await PostsService.addPost({
        title: this.title,
        description: this.description
      })
      this.$router.push({ name: 'Posts' })
    }
  }
}
</script>
<style type="text/css">
.form input, .form textarea {
  width: 500px;
  padding: 10px;
  border: 1px solid #e0dede;
  outline: none;
  font-size: 12px;
}
.form div {
  margin: 20px;
}
.app_post_btn {
  background: #0d9c44;
  color: #fff;
  padding: 10px 80px;
  text-transform: uppercase;
  font-size: 12px;
  font-weight: bold;
  width: 520px;
  border: none;
  cursor: pointer;
}
</style>
