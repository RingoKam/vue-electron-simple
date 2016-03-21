<template>
  <div id="hello">
    <h1>Hello {{ msg }}</h1>
    <p>We are using node {{ versions.node }}, Chrome {{ versions.chrome }} and Electron {{ versions.electron }}.</p>
    <button @click="submit">Submit</button>
  </div>
</template>

<script>
// Define Electron objects like this:
// const BrowserWindow = remote.BrowserWindow
// const Menu = remote.require('menu')
const ipc = electron.ipcRenderer

export default {
  data () {
    return {
      msg: 'Vue + Electron!',
      versions: {
        node: remote.process.versions.node,
        chrome: remote.process.versions.chrome,
        electron: remote.process.versions.electron
      }
    }
  },

  methods: {
    submit () {
      ipc.send('submit')
    }
  }
}
</script>
