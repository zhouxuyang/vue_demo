<template>
<div>
<input type="text" v-model="newitem" @keyup.enter="add">
<button @click="add">添加</button>
</div>
</template>

<script>
export default {
  props: {
    addList: Function
  },
  name: 'Head',
  data () {
    return {
      newitem: ''
    }
  },
  methods: {
    add () {
      // 1 检查合法性
      const item = this.newitem.trim()
      if (!item) {
        alert('不能为空')
        return
      }
      // 2 生成对象 并添加
      this.addList({title: item, complete: false})
      // 3 清空输入
      this.newitem = ''
    }
  }
}
</script>
