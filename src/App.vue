<template>
  <div id="app">
    <NavBar />
    <div class="main-ctnr"></div>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'

export default {
  name: 'App',
  components: { NavBar },
}
</script>

<style lang="scss">
#app {
}
</style>
