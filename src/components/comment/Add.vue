<template>
  <div>
    姓名：
    <input v-model="name"></input><br>
    内容：
    <textarea name="" id="" cols="30" rows="10" v-model="content"></textarea><br>
    <button @click="addItem">添加</button>
  </div>
</template>

<script>
  export default {
    props: {
      addComment: Function
    },
    name: 'Add',
    data () {
      return {
        name: '',
        content: ''
      }
    },
    methods: {
      addItem () {
        //1、合法性检查
        const name = this.name.trim()
        const content = this.content.trim()
        if (!name || !content) {
          alert('用户名和内容不能为空！')
          return
        }
        //2、封装对象
        const comment = {name, content}
        //3、添加数据
        this.addComment(comment)
        //4、清空输入内容
        this.name = ''
        this.content = ''
      }
    }
  }
</script>
