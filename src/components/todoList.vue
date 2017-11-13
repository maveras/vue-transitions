<template>
  <div class="todo-list-container">
    <ul class="todo-list">
      <li class="todo-list__item" v-for="todo in todoList">
        {{todo.text}}
      </li>
    </ul>
  </div>
</template>
<script>
	export default {
    data () {
      return {
        msg: 'asdas'
      }
    },
    props: ['todoList']
  }
</script>
<style>
	.todo-list-container {
    border: solid 1px green
  }

  .todo-list__item {
    height: 30px;
    border: 1px solid red;
  }

  .todo-list__item-hide {
    height: 0px;
  }
</style>