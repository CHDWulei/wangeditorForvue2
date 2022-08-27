<template>
  <div id="app">
    <Editor
      ref="editor"
      @completeEditor='EndEdit'
    />
    <button @click="submit">提交</button>
  </div>

</template>

<script>
import Editor from './components/Editor.vue'

export default {
  name: 'App',
  components: {
    Editor
  },
  data () {
    return {
      html: ''
    }
  },
  methods: {
    EndEdit (val) {
      this.html = val
    },
    submit () {
      // 手动触发子组件的失去焦点事件
      this.$refs.editor.completeEdit()
      alert(this.html)
    }
  },
}
</script>

<style>
#app {
}
</style>
