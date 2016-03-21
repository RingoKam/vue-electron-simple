<template>
<hello></hello>
</template>

<script>
import Hello from './components/Hello'

// Define Electron objects like this:
// const BrowserWindow = remote.BrowserWindow
// const Menu = remote.require('menu')
const ipc = electron.ipcRenderer

export default {
  components: {
    Hello
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}
</style>
