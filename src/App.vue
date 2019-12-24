<template>
  <div id="q-app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      version_dtd4: process.env.VERSION_DTD4
    }
  },
  mounted () {
    this.verificaVersaoNoCache()
  },
  methods: {
    verificaVersaoNoCache () {
      if (localStorage.getItem('version_dtd4') !== this.version_dtd4) {
        localStorage.setItem('version_dtd4', this.version_dtd4)
        setTimeout(() => {
          window.location.reload(true)
        }, 200)
      }
    }
  }
}
</script>
