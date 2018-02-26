<template>
  <div>
    <header class="site-header jumbotron">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <h1>请发表对Vue的评论</h1>
          </div>
        </div>
      </div>
    </header>
    <div class="container">
      <add :addComment="addComment"> </add>
      <comment-list :comments="comments" :delete-comment="deleteComment"> </comment-list>
    </div>
  </div>
</template>

<script>
  import add from './components/add.vue'
  import list from './components/list.vue'

  export default {

    data () {
      return {
        comments: [
          {name: '张三', content: 'Vue还不错'},
          {name: '李四', content: 'Vue真不错'},
          {name: '王五',content:'Vue好难啊'},
          {name: '刘六',content:'Vue好难啊'}
        ]
      }
    },

    methods: {
      addComment (comment) {
        this.comments.unshift(comment)
      },
      deleteComment (index) {
        this.comments.splice(index, 1)
      }
    },

    components: {
      "Add": add,
      "CommentList": list
    }
  }
</script>

<style>

</style>
