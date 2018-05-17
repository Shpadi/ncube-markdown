<template>
  <div id="app">

    <MarkDown />
  </div>
</template>

<script>
import Vue from 'vue'
import MarkDown from './components/Markdown.vue'

Vue.component('MarkDown',MarkDown);
export default {
  name: 'app',

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
