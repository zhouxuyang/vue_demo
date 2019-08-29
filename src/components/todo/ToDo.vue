<template>
  <div>
      <h2>ToDo</h2>
    <Head :addList="addList"/>
    <List :lists="lists" :changeComplete="changeComplete" :deleteComplete="deleteComplete"/>
    <Footer :lists="lists" :deleteCompleteLists="deleteCompleteLists" :selectAll="selectAll"/>
  </div>
</template>

<script>

import Head from './Head'
import List from './List'
import Footer from './Footer'

export default {
  name: 'ToDo',
  components: {
    Head,
    List,
    Footer
  },
  data () {
    return {
      // 从localstorage读取lists
      lists: JSON.parse(window.localStorage.getItem('lists_key') || '[]')
    }
  },
  methods: {
    addList (item) {
      this.lists.unshift(item)
    },
    changeComplete (index, item) {
      this.lists.splice(index, 1, item)
    },
    deleteComplete (index) {
      this.lists.splice(index, 1)
    },
    deleteCompleteLists () {
      this.lists = this.lists.filter(item => !item.complete)
    },
    selectAll (isCheck) {
      this.lists.forEach(function (todo) {
        todo.complete = isCheck
      })
    }
  },
  watch: {
    lists: {
      // 深度监视
      deep: true,
      handler: function (newValue, oldValue) {
        // 保存到localstorage中
        window.localStorage.setItem('lists_key', JSON.stringify(newValue))
      }
    }

  }

}

</script>

<style>

</style>
