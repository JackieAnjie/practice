<template>
  <div id="app">
    <Sidebar/>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar';

export default {
  name: 'app',
  components: {
    Sidebar
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin:0;
  padding:0;
}

body {
  font-family:Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
