<template>
  <div id="app">
    <leftCompo :menuToggled="menuToggled"></leftCompo>
    <button @click="showList =! showList"> toggle list</button>
    <button @click="menuToggled  =! menuToggled">toggle menu</button>
    <transition name='fade'>
      <todo-list v-if="showList" :todoList="todoList">
      </todo-list>
    </transition>
    <h2>Components change</h2>
    <div class="compo-changer-nav">
      <button @click="compMounted = 'addCompo'"> add</button>
      <button @click="compMounted = 'editCompo'"> edit</button>
      <button @click="compMounted = 'showCompo'"> show</button>
    </div>
    <div class="compo-container">
      <transition>
        <component :is="compMounted" name="drag"></component>
      </transition>
    </div>
  </div>
</template>
<script>
import todoList from './components/todoList.vue'
import leftCompo from './components/leftCompo.vue'
import addCompo from './components/addCompo.vue'
import editCompo from './components/editCompo.vue'
import showCompo from './components/showCompo.vue'

export default {
  name: 'app',
  data () {
    return {
      msg: ' to Your Vue.js App',
      showList: true,
      menuToggled : false,
      compMounted: 'addCompo',
      todoList:[
        { text: 'text 1' , done: false},
        { text: 'text 2' , done: false},
        { text: 'text 3' , done: false}
      ]
    }
  },
  methods: {
    toggleMenu () {
      this.menuToggled != this.menuToggled
    }
  },
  components:{
    todoList,
    leftCompo,
    showCompo,
    addCompo,
    editCompo
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
    .compo-container {
      background: #1E2D3A;
      width: 200px;
      height: 350px;
      border: solid 1px black;
      color: #838C94;
    }

    .drag-enter-active {
      transition: all .3s ease;
    }
    .drag-leave-active {
      transition: all .3s ease;
    }
    .drag-enter, .drag-leave-to
    {
      transform: translateY(200px);
      opacity: 0;
    }
</style>
