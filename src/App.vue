<template>
  <div id="app">
        <MyListView />
        <FileUpload />
  </div>
</template>

<script>
import MyListView from './components/MyListView.vue'
import FileUpload from './components/FileUpload.vue'
export default {
  name: 'App',
  components: {
    MyListView,
    FileUpload 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
