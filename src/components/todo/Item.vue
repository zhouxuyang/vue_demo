<template>
  <li @mouseenter="handShow(true)" @mouseleave="handShow(false)" :style="{background: bgcolor}">
      <input type="checkbox" v-model="item.complete">{{item.title}}
      <button v-show="isShow" @click="deleteItem">删除</button>
    </li>
</template>

<script>
export default {
  props: {
    item: Object,
    changeComplete: Function,
    deleteComplete: Function,
    index: Number
  },
  name: 'Item',
  data () {
    return {
      bgcolor: 'white',
      isShow: false
    }
  },
  methods: {
    handShow (value) {
      if (value) {
        this.bgcolor = '#F00'
        this.isShow = true
      } else {
        this.bgcolor = 'white'
        this.isShow = false
      }
    },
    deleteItem () {
      if (window.confirm(`确认要删除${this.item.title}`)) {
        this.deleteComplete(this.index)
      }
    }
  }

}
</script>

<style>

</style>
