<template>
  <div>
<p>
  <input type="checkbox" v-model="isCheck">
  已完成{{completeSize}}/全部{{lists.length}}
  <button @click="deleteCompleteLists" v-if="completeSize">清除已完成</button>
  </p>
  </div>
</template>

<script>
export default {
  props: {
    lists: Array,
    deleteCompleteLists: Function,
    selectAll: Function
  },
  name: 'Footer',
  computed: {
    completeSize () {
      // return this.lists.reduce((a, b) => a + (b.complete ? 1 : 0), 0)
      return this.lists.reduce(function (a, b) {
        return a + (b.complete ? 1 : 0)
      }, 0)
    },
    isCheck: {
      get () {
        return this.completeSize === this.lists.length && this.lists.length > 0
      },
      set (value) {
        this.selectAll(value)
      }
    }
  }
}
</script>

<style>

</style>
