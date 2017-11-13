<template>
  <div id="app">
    <button @click="showList =! showList"> show list</button>
    <transition name='fade'>
      <todo-list v-if="showList">
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
      showList: true
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
