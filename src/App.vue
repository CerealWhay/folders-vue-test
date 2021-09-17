<template>
  <div class="container">
    <div class="main-wrapper">
      <FolderView name="$" :folders="folders" :files="files" />
    </div>
  </div>
</template>

<script>
import FolderView from './components/FolderView.vue'
import data from './data/list';

export default {
  name: 'App',
  components: {
    FolderView
  },
  data: () => data
}
</script>

<style lang="scss">
html, body {
  background-color: #f9fbfc;
  margin: 0;
  padding: 0;
  .container {
    max-width: 1110px;
    padding: 15px 15px;
    margin: 0px auto;
    .main-wrapper {
      background-color: white;
      padding: 15px;
      border-radius: 15px;
      box-shadow: 0px 1px 7px 1px rgba(0, 0, 0, 0.1);
    }
  }
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
