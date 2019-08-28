<template>
  <div>
    <ul>
      <Item v-for="(comment,index) in comments" :comment="comment" :key="index" :deleteComment="deleteComment"/>
    </ul>
  </div>
</template>

<script>
  import Item from './Item'

  export default {
    props: {
      comments: Array,
      deleteComment: Function
    },
    name: 'List',
    components: {
      Item
    }
  }
</script>
