<template>
  <ul>
      <Item v-for="(item,index) in lists" :key="index" :index="index" :item="item" :changeComplete="changeComplete" :deleteComplete="deleteComplete"/>
  </ul>
</template>

<script>

import Item from './Item'

export default {
  props: {
    lists: Array,
    changeComplete: Function,
    deleteComplete: Function
  },
  name: 'List',
  components: {
    Item
  }
}
</script>

<style>

</style>
