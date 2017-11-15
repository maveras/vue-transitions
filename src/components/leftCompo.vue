<template>
<div :class="['menu', {'menu--toggled': menuToggled}]" >
  <ul class="menu__list">
    <li class="list__item">
      <span>item 1</span>
    </li>
  </ul>
</div>
</template>
<script>
  export default {
    data () {
      return {

      }
    },
    props: ['menuToggled']
  }
</script>
<style>
  .menu {
    width:300px;
    background: #1B2D3B;
    height: 100px;
    color: #838C94;
    display: inline-block;
    vertical-align: top;
    padding: .5rem;
    transform: translateX(-281px);
    transition: all 0.2s ease
  }

  .list-item {
    display: inline-block;
    list-style: none;
  }

  .menu--toggled {
    transform: translateX(0px);
  }
</style>