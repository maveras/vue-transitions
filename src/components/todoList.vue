<template>
  <div class="todo-list-container">
    <ul class="todo-list">
      <transition-group name="slide">
        <li class="todo-list__item" v-for="todo in todoList" :key="todo.text" v-if="!todo.done">
          {{todo.text}} <button @click="doneTask(todo)"> done </button>
        </li>
      </transition-group>
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
    methods: {
      doneTask (todo) {
        todo.done = true
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

  /* Enter and leave animations can use different */
  /* durations and timing functions.              */
  .slide-enter-active {
    transition: all .3s ease;
  }
  .slide-leave-active {
    transition: all .3s ease;
  }
  .slide-enter, .slide-leave-to
  {
    transform: translateY(10px);
    opacity: 0;
  }

</style>