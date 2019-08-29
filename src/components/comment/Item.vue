<template>
  <li>
    {{comment.name}} -*- {{comment.content}} --
    <button @click="deleteItem">删除</button>
  </li>
</template>

<script>
export default {
  props: {
    comment: Object,
    index: Number,
    deleteComment: Function
  },
  name: 'Item',
  methods: {
    deleteItem () {
      const comment = this.comment
      if (window.confirm(`确认删除${comment.name}的评论吗？`)) {
        this.deleteComment(this.index)
      }
    }
  }
}
</script>
