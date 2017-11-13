<template>
  <div id="app">
    <button @click="showList =! showList"> toggle list</button>
    <transition name='fade'>
      <todo-list v-if="showList" :todoList="todoList">
      </todo-list>
    </transition>
  </div>
</template>
<script>
import todoList from './components/todoList.vue'
export default {
  name: 'app',
  data () {
    return {
      msg: ' to Your Vue.js App',
      showList: true,
      todoList:[
        { text: 'text 1' , done: false},
        { text: 'text 2' , done: false},
        { text: 'text 3' , done: false}
      ]
    }
  },
  components:{
    todoList
  }
}
</script>

<style>
    .fade-enter-active, .fade-leave-active {
      transition: opacity .5s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
      opacity: 0
    }
</style>
