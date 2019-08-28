<template>
  <div>
    <h4>添加评论：</h4>
    <Add :addComment="addComment"/>
    <h4>评论区：</h4>
    <p v-show="comments.length==0">暂无评论！</p>
    <List :comments="comments" :deleteComment="deleteComment"/>
  </div>
</template>

<script>
  import List from './List'
  import Add from './Add'

  export default {
    name: 'UserComment',
    data () {
      return {
        comments: [
          {name: 'user1', content: 'content1'},
          {name: 'user2', content: 'content2'},
          {name: 'user3', content: 'content3'}
        ]
      }
    },
    components: {
      List,
      Add
    },
    methods: {
      addComment (comment) {
        this.comments.unshift(comment)
      },
      deleteComment (index) {
        this.comments.splice(index, 1)
      }
    }
  }
</script>

<style>
    div{
      width: 400px;
    }
</style>
